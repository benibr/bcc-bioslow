## BCC Block I/O slow request logging

A python script using BPF to log I/O latency.

This tool fits in the collection of [bcc tools](https://github.com/iovisor/bcc) where some script to measure I/O requests already exist,
however `bioslow` lets you specify a threshold and logs all I/O requests which take longer than that.

```
usage: bioslow [-h] [-t THRESHOLD] [-l LOGFILE] [-u {us,ms,s}]

Log slow I/O operations over a given threshold

optional arguments:
  -h, --help            show this help message and exit
  -t THRESHOLD, --threshold THRESHOLD
                        log requests which took longer than this (default: 1µs)
  -l LOGFILE, --logfile LOGFILE
                        log to a given file instead of stdout
  -u {us,ms,s}, --unit {us,ms,s}
                        unit of threshold and reported times. Can be 'us', 'ms' or 's'

examples:
    ./bioslow                    # print latency of I/O operations
    ./bioslow -t 10              # print I/O operations longer than 10us
    ./bioslow -t 100 -u ms       # print I/O operations longer than 100ms
    ./bioslow -l foo.log         # log to a file instread of stdout
```
