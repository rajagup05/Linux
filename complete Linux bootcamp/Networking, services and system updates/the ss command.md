
## the `ss` command

The ss command (Socket Statistics) is a powerful Linux command-line utility used to dump socket statistics, display detailed information about network connections, and monitor open ports. It serves as the modern, faster, and highly efficient replacement for the deprecated netstat command by pulling data directly from kernel space using the netlink interface.

### 🛠️ Common Option Flags

- `-a`: Displays both listening and non-listening sockets.
- `-l`: Shows only listening sockets (which are waiting for incoming connections).
- `-t`: Filters for TCP connections.
- `-u`: Filters for UDP connections.
- `-n`: Shows raw numerical port numbers and IP addresses instead of resolving them into names (e.g., 22 instead of ssh).
- `-p`: Lists the process name and Process ID (PID) utilizing the socket.
- `-s`: Prints a summary overview of overall network statistics.

### 💻 Examples

- To see all listening ports, their corresponding numeric port numbers, and the specific programs running them, run: `sudo ss -tulpn`
- View All TCP or UDP Connections

```
ss -at      # All TCP connections (listening and established)
ss -au      # All UDP connections
```

- Filter by Active Network State: `ss -t state established`
- Filter by Specific Port:

```
ss -ltn sport = :22      # Checks if something is listening locally on port 22 (SSH)
ss -tn dport = :443      # Checks outbound connections going to a remote HTTPS port
```

- View Quick Network Statistics Summary: `ss -s`
  
