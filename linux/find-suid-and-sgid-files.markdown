# Find SUID and SGID Files

SUID and SGID files on your system are a potential security risk, and should be
monitored closely. Some programs require this functionality, which is why I
specified that they should be monitored, and not removed. I use the following 
one-liners for both defensive and offensive purposes.

To identify SUID programs:

    $ sudo find / -perm -u=s -type f -exec ls -ld {} \; 2>/dev/null 

To identify SGID programs:

    $ sudo find / -perm -g=s -type f -exec ls -ld {} \; 2>/dev/null 

'''Defensive:''' The results provided should be used to create a baseline in order
to pinpoint any additions, deletions or modifications to the SUID/SGID programs on
your systems. Any changes could indicate a potential attacker or misconfiguration
and should be investigated further. 

'''Offensive:''' These are also extremely useful during pentests when looking
to escalate privileges on a linux system. Finding a script with these permissions
set could grant elevated access, which could help to own the system.
