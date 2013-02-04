Growl notifier for jenkins

## Build Status

[![Build Status](https://travis-ci.org/katta/jenkinsgrowler.png?branch=master)](https://travis-ci.org/katta/jenkinsgrowler)

## Installation

### Prerequisites

Grown notifier command line tool has to be installed and is available on path.

### Installing from rubygems

```ruby
gem install jenkinsgrowler
```

### Building from source

```bash
$ git clone https://github.com/katta/jenkinsgrowler.git
$ cd jenkinsgrowler
$ rake
$ gem install pkg/jenkinsgrowler.gem
```

# Running

```bash
Usage: jenkinsgrowler [options]
    -s, --server SERVER_URL          URL of the jenkins server
    -j, --jobs JOBS                  Comma separated jobs names
    -i, --interval INTEVAL           Polling interval in seconds. Default (60 secs)
    -u, --user USERNAME              Username for basic authentication
    -p, --password PASSWORD          Password for basic authentication
    -h, --help                       Displays help message
```

## Examples

### Provide server url and job names to be monitored

```bash
$ jenkinsgrowler -s "http://old-ci.motechproject.org/" -j "GrowlerTest"
```

In the above example the `http://ci.myhost.com/` is the jenkins continuous integration server url and `GrowlerTest` is a job name ot be monitored.

You can also monitor more than one job by specifying comma spearate job names like 

```bash
$ jenkinsgrowler -s "http://old-ci.motechproject.org/" -j "GrowlerTest, Job3"
```

### Basic authentication

If your ci server is protected with basic authentication, you could just pass on the credentials to the `jenkinsgrowler` as shown below

```bash
$ jenkinsgrowler -s "http://old-ci.motechproject.org/" -j "GrowlerTest" -u "username" -p "password"
```
