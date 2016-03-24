# Add Date and Time to History

After an IR engagement, I always look back and reflect on what I could have done
better. It's great to keep detailed notes and logs, but when constructing a response
timeline, I consistently ask myself, "When did I run that command?" Adding date
and time to your history can assist with this. 

Simply set the <code>HISTTIMEFORMAT</code> variable:

    $ HISTTIMEFORMAT="%Y%m%d %T "

The history file will now look like this:

    $ history | tail
    504  20160323 22:14:54 pwd
    505  20160323 22:14:54 ls
    506  20160323 22:14:57 uname -a

I prefer the format YYYYMMDD, but you can modify the <code>HISTTIMEFORMAT</code>
variable just like you would with the date command. This change is only effective
in the current shell, so add this line to your bashrc file to make it permanent:

    export HISTTIMEFORMAT="%Y%m%d %T "

