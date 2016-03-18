# Inserting Command Output Into a File

Sometimes when you are editing a file in vim you need to insert the date or output
from a specific command. You can run commands from vim's command mode.

For example, if I was creating a file for evidence I may want to append the date
to the top of the file. I would do so by typing:

```bash
:.! date
```

The output will look like this:

```bash
Thu Mar 17 23:37:43 EDT 2016
foo
bar
biz
```
Be aware that the command output will be placed where the cursor is located.
