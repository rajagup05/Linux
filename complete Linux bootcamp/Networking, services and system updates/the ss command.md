
## the `ss` command

The ss command (Socket Statistics) is a powerful Linux command-line utility used to dump socket statistics, display detailed information about network connections, and monitor open ports. It serves as the modern, faster, and highly efficient replacement for the deprecated netstat command by pulling data directly from kernel space using the netlink interface.

### 🛠️ Common Option Flags

- `-a`: Displays both listening and non-listening sockets.
- `-l`: Shows only listening sockets (which are waiting for incoming connections).
- `-t`: Filters for TCP connections.
- `-u`: Filters for UDP connections.
