# Generating Messages with Logger

Syslog is an extremely useful utility. Logger is a shell command interface to 
the syslog system log module. It can assist with testing different logging facilities
or just sending a token to determine what system is logging where. The command
format is very simple:

    $ logger "foo bar biz baz"

I started up a quick <code>tail -f</code> to catch the message:

    $ tail -f /var/log/messages
    Mar 21 15:37:53 test-machine logger: foo bar biz baz

As you can see the message appears in <code>/var/log/messages</code>. The are other
flags that can set the priority (-p), tag the message (-t), and log the process
id (-i). 

One of the best features of logger is its ability log command output to syslog. I
have used this feature to log system admin and security checks to a centralized
location. As a short example I will log the output of the date command to logger:

    $ date | logger
    
Let's check the output:

    $ tail -f /var/log/messages
    Mar 21 15:54:16 test-machine logger: Mon Mar 21 15:54:16 EDT 2016

Now this is a very simple example but imagine the applications of piping output
to logger. If you needed to run a check for any SETUID/SETGID files in your
environment of 50 systems you could create a search script that outputs to logger
and simply check your centralized syslog collector for the results.
