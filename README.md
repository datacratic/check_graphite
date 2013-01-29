Nagios plugin to poll Graphite
===

What does it do? How does it work? How do I run it?
---

This is a Nagios plugin, so you install it and configure a service check in Nagios and it runs whenever Nagios calls it and reports back on the status of whatever it's monitoring. It has one required parameter (`-u`) which tells it the Graphite URL to monitor, for example `http://server/render?target=stats.auctionStart&from=-1minutes&rawData=true`. When run, it will query that URL and treat the average of the values returned as the 'value' to be compared against the warning/critical thresholds, and return this value to Nagios as performance data. See Graphite's URL API documentation to generate the URL parameter.

Usage
---
Usage: check_graphite -u URL [-U USERNAME] [-P PASSWORD] [-H HOSTNAME] [-n NONE] [-f FUNCTION] [-w WARNING] [-c CRITICAL]

Plugin to retrieve data from graphite

Options:
`    -h, --help            show this help message and exit  
    -V, --version         show program's version number and exit  
    -v, --verbose         Get more verbose status output. Can be specified up to three times  
    -u URL, --url=URL     URL to query for data  
    -U USERNAME, --username=USERNAME User for authentication  
    -P PASSWORD, --password=PASSWORD Password for authentication  
    -H HOSTNAME, --hostname=HOSTNAME Host name to use in the URL  
    -n NONE, --none=NONE  Ignore None values: 'yes' or 'no' (default no)  
    -f FUNCTION, --function=FUNCTION Function to run on retrieved values: avg/min/max/last/sum (default 'avg')  
    -w WARNING, --warning=WARNING Set the warning notification level.  
    -c CRITICAL, --critical=CRITICAL Set the critical notification level.  `

Dependencies
---

Python 2.6+

You'll need to have NagAconda installed (e.g. `easy_install nagaconda`)
