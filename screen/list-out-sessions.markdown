# List Out Sessions

To list out your screen sessions run <code>screen -ls</code>:

      $ screen -ls
      There are screens on:
      	23634.test3	(04/11/2016 09:27:38 PM)	(Detached)
      	23620.test2	(04/11/2016 09:27:35 PM)	(Detached)
      	23606.test1	(04/11/2016 09:27:30 PM)	(Detached)
      3 Sockets in /var/run/screen/S-foo.

To reconnect a session just run <code>screen -r</code> with the name or number. 

For example:

      $ screen -r test3
