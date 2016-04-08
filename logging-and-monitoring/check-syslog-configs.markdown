# Check Syslog Configs

Making changes to syslog configs can be dangerous. A simple typo in a new filter 
could cause a major logging disruption, so it helps to run a quick syntax check
before restarting the service.

To run a syntax check with rsyslog, run the following commands:

    $ rsyslogd -N1
    $ echo $?

Here is the equivalent commands for syslog-ng:

    $ syslog-ng -s
    $ echo $?

<code>$?</code> will contain the exit status of the last command executed. A quick
example will show how this works.

    $ true; echo $?
    0
    $ false; echo $?
    1

A successful command will return a 0, while an unsuccessful one will return a 
non-zero value indicating an error code. If the command <code>echo $?</code> 
returns a 0 we are good to restart the service, but any non-zero number would
warrant additional investigation. 
