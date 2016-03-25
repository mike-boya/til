# Converting EVTX to CSV

I perform the majority of my forensics analysis from linux command line so when
I am provided with Windows logs in the EVT/EVTX format I convert them to CSV. 

This can be done with the log2timeline tool.

      $ log2timeline -h


      -------------------------------------------------
      Usage:
          log2timeline [OPTIONS] [-f FORMAT] [-z TIMEZONE] [-o OUTPUT MODULE] [-w
          BODYFILE] LOG_FILE/LOG_DIR [--] [FORMAT FILE OPTIONS]

The usage is very straight forward, simply pass the file to log2timeline, specifying
the format, timezone, and output file.

The timezone format is intuitive but if you would like to see all available options
you can list them out with this command:

      $ log2timeline -z list | less

I've included an example for reference:

      $ log2timeline System.evtx -f evtx -z PST8PDT -w System.csv

As I'm sure you know the CSV file can be opened in excel or parsed and manipulated
using normal command line utilities. 
