# Run Urlsnarf Against a Pcap

Examining pcap files for unique information is a very useful skill. *Urlsnarf* is a tool that
collects HTTP request data, from an interface or pcap, and stores it in CLF (common log format).
Searching through multiple pcaps for a specific request or gathering a detailed summary of
activity that took place is easy with this simple tool. 

The first step is to install Dsniff tools with apt-get: 

```bash
$ sudo apt-get install dsniff
```

Then, run *urlsnarf* with the <code>-p</code> flag:

```bash
$ urlsnarf -p conference.pcapng
urlsnarf: using conference.pcapng [tcp port 80 or port 8080 or port 3128]
172.16.254.128 - - [17/Mar/2015:16:42:53 -0400] "GET http://www.reddit.com/ HTTP/1.1" - - "-" "Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/41.0.2272.89 Safari/537.36"
```
It is important to note that collecting and storing syslog will contain all of this data, but
the technique provides value when all you have available is packet capture. In most situations
this will not be the case, but this method can assist with getting a clearer picture during
forensic CTFs and honeypot captures.
