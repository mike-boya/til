# cd -

Most of the time when I am moving between directories I use pushd and popd, but sometimes if I am in a rush I default back to cd. Some directories can have really long paths so a quick
time saver is 'cd -'.

This will simply return you to your previous directory. Here is an example:

```bash
mike@foo:~$ cd 7/8/9/10/11/12
mike@foo:~/7/8/9/10/11/12$ cd /home/mike/1/2/3/4/5/6/
mike@foo:~/1/2/3/4/5/6$ cd -
/home/mike/7/8/9/10/11/12
mike@foo:~/7/8/9/10/11/12$
```
Running that command brought us back to the directory '/home/mike/7/8/9/10/11/12', which saved some typing and time.
