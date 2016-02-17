# !! and !$ 

I am a big fan of these two shortcuts and use them daily.

## !!

This *repeats* the last command run. This is my go-to if I forget to run a command as sudo.

```bash
$ touch /etc/foo
touch: cannot touch ‘/etc/foo’: Permission denied
$ sudo !!
sudo touch /etc/foo
```

## !$

This one will subsitute the last word of the previous command. I use this when I am running multiple commands on a file.

```bash
$ touch foo.txt
$ vi !$
vi foo.txt
```
