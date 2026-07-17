
## ps command

The ps command (Process Status) in Linux provides a static point-in-time snapshot of currently running processes on your system. Unlike interactive commands like top or htop, ps does not update in real-time, making it ideal for scripting, automation, and piping with other utilities like grep.

### 1. Default (No Options)

- `ps`: Displays only the processes running in your current terminal session.

### 2. View Every System Process

- `ps aux`: `a`-> Shows processes for all users. `u`: Displays user-oriented format (includes CPU and memory usage columns). `x`: Lists processes not attached to a terminal (such as system daemons).Best Used For: Checking memory and CPU consumer spikes

### 3. View Every System Process

- `ps -ef`: `-e`: Selects all processes running on the system. `-f`: Generates a full-format listing.

### Search for a Process by Name

`ps aux | grep nginx`
