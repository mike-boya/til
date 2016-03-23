# Be Careful with Usermod

Today I learned that using the usermod command to add a group to an existing
user without specifying the <code>-a</code> flag is very dangerous. I created a
new group, called logs, on my machine and wanted my user added. I issued <code>
usermod -G</code> to add the test user to the logs group.

    $ usermod -G logs test

Then I received this error when trying to sudo:

    $ sudo ls
    [sudo] password for test:
    test is not in the sudoers file.  This incident will be reported.

How strange. I checked the logs:

    $ less /var/log/messages
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from group 'adm'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from group 'cdrom'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from group 'sudo'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from group 'dip'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from group 'plugdev'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from group 'libvirtd'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from group 'lpadmin'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from group 'sambashare'
    Mar 20 00:51:45 test-machine usermod[7300]: add 'test' to group 'logs'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from shadow group 'adm'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from shadow group 'cdrom'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from shadow group 'sudo'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from shadow group 'dip'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from shadow group 'plugdev'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from shadow group 'libvirtd'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from shadow group 'lpadmin'
    Mar 20 00:51:45 test-machine usermod[7300]: delete 'test' from shadow group 'sambashare'
    Mar 20 00:51:45 test-machine usermod[7300]: add 'test' to shadow group 'logs'

Wow! So adding a user to one group removed the user from all other groups. Please note
that this was performed on a default Ubuntu 14.04 install.

Using the<code>-G</code> option alone, will remove all existing groups that user
belongs. Always add the <code>-a</code> (append) with <code>-G</code> option to
add or append new groups.

The correct syntax would be:

      $ usermod -a -G logs test

Now, if you run the command without the <code>-a</code> flag and force yourself
out of the sudo group you will need to either re-add yourself to the group from
another account with sudo access or boot into a root shell and make the change.
