When starting a new screen session use the <code> -S </code> flag to name it:

bash```
$ screen -S <name>
```

For example:
bash```
$ screen -S irc
$ screen -ls
There is a screen on:
	18444.irc	(02/24/2016 11:11:31 PM)	(Detached)
1 Socket in /var/run/screen/S-foo.
```

This is helpful when running multiple log searches in screen. To reattach:

bash```
$ screen -r irc
```
