## No longer maintained...

We no longer use this script internally so we are no longer maintaining it. Unfortunately, that means we won't accept any pull requests, but if you make some improvements, we would be happy to link to your repo.

Here are some forks which have useful improvements:

* Support for multiple lines: https://github.com/olivierHa/check_graphite

## Nagios plugin to poll Graphite

### What does it do? How does it work? How do I run it?

This is a Nagios plugin, so you install it and configure a service check in Nagios and it runs whenever Nagios calls it and reports back on the status of whatever it's monitoring. It takes one parameter (`-u`) which tells it the Graphite URL to monitor, for example `http://server/render?target=stats.auctionStart&from=-1minutes&rawData=true`. When run, it will query that URL and treat the average of the values returned as the 'value' to be compared against the warning/critical thresholds, and return this value to Nagios as performance data. See Graphite's URL API documentation to generate the URL parameter.

### Dependencies

Python 2.6+

You'll need to have NagAconda installed (e.g. `easy_install nagaconda`)
