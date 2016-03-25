# MARKing with Syslog

Syslog sends a lot of messages, but how can you tell if those messages stop or it
is just quiet evening? This issue was affecting my syslog setup and I was about
to write up a short log beacon until my co-worker mentioned MARK, syslogs
heartbeat. I performed the following test on rsyslog 7.4.4. 

In order to enable MARK, I uncommented this line in <code>/etc/rsyslog.conf</code>

    $ModLoad immark  # provides --MARK-- message capability

Next, I added this line:

    $MarkMessagePeriod  60 # mark messages appear every 10 Minutes

After restarting the syslog service I checked the logs:

    $ tail -f /var/log/messages
    Mar 21 13:21:09 test-machine rsyslogd: -- MARK --
    Mar 21 13:51:09 test-machine rsyslogd: -- MARK --

One item of note, MARK messages will only be sent if a log file is not being
written to frequently. If you would like to have all MARK messages logged you
will need to add <code>$ActionWriteAllMarkMessages</code> to your config file.
