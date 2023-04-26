# Fake Apache Log Generator

This script generates a boatload of fake apache logs very quickly. Its useful for generating fake workloads for [data ingest](http://github.com/streamsets/datacollector) and/or analytics applications.

It can write log lines to console, to log files or directly to gzip files.

It utilizes the excellent [Faker](https://github.com/joke2k/faker/) library to generate realistic ip's, URI's etc.

***

## Basic Usage

Generate a single log line to STDOUT
```
$ python apache-fake-log-gen.py  
```

Generate 100 log lines into a .log file
```
$ python apache-fake-log-gen.py -n 100 -o LOG 
```

Infinite log file generation (useful for testing File Tail Readers)
```
$ python apache-fake-log-gen.py -n 0 -o LOG 
```

Prefix the output filename 
```
$ python apache-fake-log-gen.py -n 100 -o LOG -p WEB1
```


Detailed help
```
$ python apache-fake-log-gen.py -h
usage: apache-fake-log-gen.py [-h] [--output {LOG}]
                              [--num NUM_LINES] [--prefix FILE_PREFIX]
                              [--sleep SLEEP]

Fake Apache Log Generator

optional arguments:
  -h, --help            show this help message and exit
  --output {LOG}, -o {LOG}
                        Write to a Log file
  --num NUM_LINES, -n NUM_LINES
                        Number of lines to generate (0 for infinite)
  --prefix FILE_PREFIX, -p FILE_PREFIX
                        Prefix the output file name
  --sleep SLEEP, -s SLEEP
                        Sleep this long between lines (in seconds)
```


## Requirements
* Python 3.11
* ```pip install -r requirements.txt```
