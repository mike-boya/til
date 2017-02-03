# Save Command To History Without Running It

Typing out a long command and having to Ctrl+C to collect additional information from the shell can be frustrating and inefficient. I'm sure everyone has little solutions like copying before deleting, or opening another terminal. 

I located a tip which will allow you to save the output without running the command. In order to save your command without running it just use 'history -s <COMMAND>'.

Here is a quick example:

```bash
$ history -s echo foo
```

No output is returned because the command was not executed. However, if you hit the up arrow-key you will be presented with the command as if you ran it.

Let's run the previous command now:

```bash
$ echo foo
foo
```
There are other ways to accomplish this but I really appreciated this solutions use of history.
