# Append Today's Date to a Filename

I run a lot of log searches during my daily tasks and in order to keep track
of my work I normally append a date to my output files. It also saves me some
keystrokes when typing up my daily notes. 

Check the *date* man page to determine what FORMAT works best for you.

```bash
$ echo "foo" > notes_$(date +%F).txt
```

Let's check the output:

```bash
$ ls
notes_2016-02-11.txt
$ cat notes_2016-02-11.txt
foo
```
