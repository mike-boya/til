# Using Time

The time command executes the given command or program.

      $ time ls
      foo bar biz baz bang

      real	0m0.004s
      user	0m0.004s
      sys	  0m0.000s

This command is extremely useful and I have found it effective and helpful when
calculating efficiency of similar commands. Additional output can be specified by
modifying the format string with the <code>-f</code> flag. "P" has proven itself 
useful and outputs the percentage of the CPU used.
