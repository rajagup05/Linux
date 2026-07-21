
## system monitoring commands (df, dmesg, iostat, netstat, free, top)

In Linux, df, dmesg, iostat, netstat, free, and top are foundational command-line utilities used by system administrators to monitor storage, kernel events, input/output performance, network routing, memory allocation, and active processes in real time.

### 1. `df` (Disk Free)

The df command monitors disk space capacity across all mounted filesystems. It helps detect full disks before they crash your applications.

`df -h`: Shows disk usage in easy-to-read gigabytes (GB) and megabytes (MB).

### 2. `dmesg` (Diagnostic Messages)

The dmesg command inspects kernel-level events and hardware-driver activities. It is critical for debugging newly attached hardware, boot errors, or Out-Of-Memory (OOM) process kills.

`dmesg -T`: Converts the default raw boot-seconds timestamps into standard human dates.

`dmesg | grep -i error`: Filters the entire buffer stream strictly for error alerts.
