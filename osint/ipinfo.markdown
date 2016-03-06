# Perform IP Lookups with Ipinfo

The isn't really a "Today I Learned", but I have shown this tool to a few friends and 
each one has mentioned what a great addition it was to their toolkit.

I figured I would share it here to inform more people.

```bash
$ curl ipinfo.io/8.8.8.8
{
  "ip": "8.8.8.8",
  "hostname": "google-public-dns-a.google.com",
  "city": "Mountain View",
  "region": "California",
  "country": "US",
  "loc": "37.3845,-122.0881",
  "org": "AS15169 Google Inc.",
  "postal": "94040"
}
```
The JSON output is very useful and allows for quick lookups. 

Appending <code>/org</code> to the URL provides just the org:

```bash
$ curl ipinfo.io/8.8.8.8/org
AS15169 Google Inc.
```
The basic (free) access allows 1,000 daily requests which is more than enough for
quick analysis. Personally, I have never hit the 1,000 request limit.

The standard output and command line access allows for simple scripting to get the
information you need.
