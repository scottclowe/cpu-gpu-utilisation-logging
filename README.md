# CPU and GPU utilisation logging

Logs GPU and CPU utilization, either to stdout or to a CSV file.

```sh
log_gpu_cpu_stats  [OPTION1 [ARG1]] [OPTION2 [ARG2]] ... [FILE]
```

## Usage

```sh
log_gpu_cpu_stats
log_gpu_cpu_stats -l 10
log_gpu_cpu_stats compute_usage_log.csv
log_gpu_cpu_stats --no-header -l 5 -n 60 compute_usage_log.csv
```

## Options

```
-h, --help          Show usage and exit.

--loop <INTERVAL>
-l <INTERVAL>       Loop every INTERVAL seconds. Default is 1 second.

--niter <MAXITER>
-n <MAXITER>        Repeat at most MAXITER times. Default is -1,
                    which corresponds to forever (send interrput signal
                    to terminate).

-H, --no-header     Disable header in table output. Default is enabled.

--header            Enable header in table output. Default is enabled.

-c, --csv           Output in csv style. Default style is csv if FILE is
                    set.

-t, --tabular       Output in ascii table style. Default style is tabular
                    if FILE is not set (output is sent to stdout).

-I, --date-iso      Show time in ISO format. Default is seconds (-s flag).

-s, --date-seconds  Show time in seconds since Unix epoch (with ms
                    precision reported). Enabled by default.

--date <FORMAT>
-d <FORMAT>         Show time in custom format, FORMAT.

[FILE]              If present, output is appended to FILE. If omitted,
                    output is sent to stdout.
```

## Requirements

- POSIX-compliant shell (tested in both bash and dash)
- nvidia-smi
- top
- bc
