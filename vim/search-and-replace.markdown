# Search and Replace

When using vim, there are times when you need to replace a string in multiple
locations within a file. For example, if you wanted to change a default log
location from <code>/var/log/foo/</code> to <code>/var/log/data/<code> you might
need to go alter 50 lines in order to cover all references to the old location.
Using the following command you can search and replace all occurrences of the
string in the config file:

```
:%s/<search_string>/<replace_string>/g
```

I grabbed a few lines from a Robert Frost poem to assist with an example.

The original file looks like this:

```bash
$ cat foo
Two roads diverged in a yellow wood,
And sorry I could not travel both
And be one traveler, long I stood
And looked down one as far as I could
To where it bent in the undergrowth;
```

After opening the file in vim, press ESC and type:
```
%s/I/we/g
```
The command equates to <code>substitute/search/replace/global</code>. The
replacement will happen instantly. I saved and quit to compare to the original
file:

```bash
$ cat foo
Two roads diverged in a yellow wood,
And sorry we could not travel both
And be one traveler, long we stood
And looked down one as far as we could
To where it bent in the undergrowth;
```

If you would like to replace a single occurrence just omit the <code>g</code> option.

There are additional flags to handle case-insensitive matching, replacement confirmation
on each string, etc.
