
## system monitoring commands (df, dmesg, iostat, netstat, free, top)

In Linux, df, dmesg, iostat, netstat, free, and top are foundational command-line utilities used by system administrators to monitor storage, kernel events, input/output performance, network routing, memory allocation, and active processes in real time.

### 1. `df` (Disk Free)

The df command monitors disk space capacity across all mounted filesystems. It helps detect full disks before they crash your applications.

`df -h`: Shows disk usage in easy-to-read gigabytes (GB) and megabytes (MB).

### 2. `dmesg` (Diagnostic Messages)

The dmesg command inspects kernel-level events and hardware-driver activities. It is critical for debugging newly attached hardware, boot errors, or Out-Of-Memory (OOM) process kills.

`dmesg -T`: Converts the default raw boot-seconds timestamps into standard human dates.

`dmesg | grep -i error`: Filters the entire buffer stream strictly for error alerts.

### 3. `iostat` (Input/Output Statistics)

Part of the sysstat package, iostat tracks storage performance bottlenecks. It exposes if a system slowdown is caused by slow physical drives despite low CPU usage.

### 4. `netstat` (Network Statistics)

Though legacy distributions are migrating toward the modern ss utility, netstat remains widely used to inspect active network sockets and routing paths.

`netstat -tulpn`: Displays all listening or active connections. It groups TCP (t), UDP (u), listening sockets (l), process IDs (p), and bypasses slow DNS resolution with numeric IPs (n).

`netstat -r`: Shows the kernel routing table directly.

### 5. `free` (Memory Status)

The free command provides an instant snapshot of your system RAM and Swap file space.

`free -h`: Displays statistics cleanly in human-friendly measurements (MB/GB).

### 6. `top` (Table of Processes)

The top utility provides an interactive, real-time dashboard displaying CPU load averages, overall uptime, and a live list of resource-heavy system processes.

`top -u username`: Filters the streaming terminal view to look exclusively at tasks run by a specific user.

Live Shortcuts: While top is running, hit `Shift + M` to sort your processes by maximum RAM consumption, or `Shift + P` to sort them by raw CPU load.






