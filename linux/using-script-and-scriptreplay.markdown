# Using Script and Scriptreplay

This is a very cool tool that I discovered during a forensics investigation. Technically
it is two tools - *script* and *scriptreplay*. *Script* records the commands typed into a terminal
session. 

The *script* tool is run like this:

```bash
$ script -t 2>foo.time foo.log
```
There are a number of options, but the command above runs the script command, passes the timing data
and standard error to a file using the <code>-t</code> flag, and writes the output to foo.log. Continue
on and type a number of commands before exiting with **ctrl-d** or 'exit'.

There are two ways to view the output. The first is to *cat* out the output file to see the commands
run and the results of those commands:

```bash
$ cat foo.log
```
The second is to 'replay' the session using *scriptreplay*:

```bash
$ scriptreplay foo.time foo.log
```
This is a cool way to watch the commands run and the results received but under a time crunch can
be overkill.

I have found these useful during Incident Response - recording output and results while I search and
perform my analysis before memorializing the items in my notes. I'm sure we all try to find the
needle in the haystack before noting what we did. This can be a good reminder if that process
takes longer than expected.
