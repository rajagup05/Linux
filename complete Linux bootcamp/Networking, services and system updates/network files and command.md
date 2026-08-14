
## network files and command

In Linux, managing network configurations and troubleshooting connectivity is done by modifying core system configuration files and executing dedicated terminal commands.

### Core Linux Network Files

These files are plain-text documents stored in the system directories that control everything from IP addresses to DNS resolution.

- `/etc/hosts` - Maps IP addresses to hostnames locally before checking external DNS.
- `/etc/resolv.conf` - Configures the IP addresses of DNS nameservers for domain resolution.
- `/etc/hostname` - Stores the permanent, unique name assigned to the local machine.
- `/etc/services` - Maps familiar service names (like HTTP or SSH) to their official port numbers.
- `/etc/nsswitch.conf` - Dictates the lookups order for hostnames, passwords, and network protocols.
- `/etc/network/interfaces` - Used by older Debian/Ubuntu configurations to define interface properties.

### 1. ping

The ping command is a terminal utility used to test if a computer or server is online and responding over a network.

#### How It Works

When you run ping, your computer sends a small packet of data called an ICMP (Internet Control Message Protocol) Echo Request

- If the target is online and reachable, it sends back an ICMP Echo Reply.
- If the target is offline, blocked by a firewall, or the network is down, the packet is lost.

#### Basic Syntax and Examples

- To test a remote website or server: `ping google.com`
- To test a specific internal or external IP address: `ping 192.168.1.1`

>[!Note]
>On Linux, ping will run indefinitely until you stop it manually by pressing Ctrl + C.

#### How to Read the Output

When you run a successful ping, you will see lines of output that look like this:
```
64 bytes from 142.250.190.46: icmp_seq=1 ttl=117 time=14.2 ms
```

- `64 bytes`: The size of the network packet sent.
- `from 142.250.190.46`: The IP address of the device responding.
- `icmp_seq=1`: The sequence number of the packet (helps identify if packets are arriving out of order or getting lost).
- `ttl=117`: Time to Live. The maximum number of network hops (routers) the packet can pass through before being dropped.
- `time=14.2 ms`: Latency (Ping rate). The exact time it took (in milliseconds) for the packet to go to the server and back. Lower numbers mean a faster connection.

#### Useful Flags (Options)

- `ping -c 4 google.com` - Stops automatically after sending exactly 4 packets (mimics Windows behavior).
- `ping -i 5 google.com` - Changes the wait interval to send a packet every 5 seconds instead of the default 1 second.
- `ping -s 1000 google.com` - Changes the packet payload size to 1000 bytes to test how the network handles larger data chunks.
- `ping -4 google.com` - Forces the command to use IPv4 addresses only.

#### Common Error Messages

- **Destination Host Unreachable**: Your computer cannot find a path/route to the target IP address (often a local network or router issue).
- **Request Timed Out / 100% packet loss**: The packet was sent, but no response came back. This happens if the target is turned off, the IP does not exist, or a firewall is intentionally blocking ping requests for security.


### 2. ifconfig

`ifconfig` (interface configuration) is a classic command-line tool in Linux used to view, configure, and manage network interfaces.

While it is heavily used in older systems and legacy tutorials, it has been deprecated in modern Linux distributions in favor of the more powerful ip command.

#### What it Does

- Displays active interfaces: Shows names, IP addresses, MAC addresses, and traffic stats.
- Configures IP addresses: Assigns static IPs or subnet masks to specific network cards.
- Enables/Disables network cards: Turns interfaces up (on) or down (off).


#### Common Usage and Examples

- View all active interfaces: `ifconfig`
- View all interfaces (including disabled ones): `ifconfig -a`
- Disable a network interface: `sudo ifconfig eth0 down`
- Enable a network interface: `sudo ifconfig eth0 up`
- Assign a static IP address and netmask: `sudo ifconfig eth0 192.168.1.50 netmask 255.255.255.0`

#### Modern Alternative: `ifconfig` vs. `ip`

Most modern Linux distributions (like Ubuntu 18.04+, RHEL 7+, Debian 10+) no longer include ifconfig by default. If you type it, you may get a "command not found" error.

- View all interfaces: `ifconfig -a` => `ip a` (or `ip address`)
- Enable an interface: `ifconfig eth0 up` => `ip link set eth0 up`
- Disable an interface: `ifconfig eth0 down` => `ip link set eth0 down`
- Assign an IP address: `ifconfig eth0 192.168.1.50` => `ip addr add 192.168.1.50/24 dev eth0`

### 3. if up or ifdown

`ifup` and `ifdown` are high-level Linux command-line utilities used to enable (bring up) or disable (take down) network interfaces based on predefined configurations

Instead of manually configuring IP addresses and routes, these commands look at your system's network configuration files (like /etc/network/interfaces) and apply all the saved settings automatically.

#### How They Work

- `ifup <interface>`: Reads the configuration for the specified network interface (e.g., eth0 or wlan0), activates the hardware, requests an IP address (via DHCP or static setup), and configures the routing rules.
- `ifdown <interface>`: Deactivates the interface, releases its IP address, clears its routing table entries, and stops network traffic on that device.

#### Common Examples

- Restart a network card (useful if your connection drops): `sudo ifdown eth0 && sudo ifup eth0`
- Bring up a Wi-Fi connection: `sudo ifup wlan0`

### 4. netstat

`netstat` (network statistics) is a classic command-line utility used to monitor and troubleshoot network connections, routing tables, and interface statistics on a Linux system.

It acts like a network security monitor, showing you exactly which apps are talking to the internet, which ports are open, and where your traffic is going.

#### What Can You Do With It?

- Find open ports: See what services (like web servers or SSH) are waiting for connections.
- Identify active connections: Check who is currently connected to your server.
- Troubleshoot apps: Figure out why a process or app cannot bind to a specific network port.

#### Common Usage and Examples

- View all active connections (TCP and UDP): `netstat -a`
- Show connections as numbers (faster, skips DNS lookup): `netstat -an`
- Find out which program/PID is using a port (requires sudo): `sudo netstat -pntle` (A popular combination: -p for program name, -n for numerical addresses, -t for TCP, -l for listening ports).
- View the network routing table: `netstat -r`

#### Modern Alternative: netstat vs. ss

Just like ifconfig, netstat is an older tool that has been deprecated in modern Linux distributions. It is part of the legacy net-tools package and has been replaced by the much faster and more accurate ss (socket statistics) command.

- List all listening TCP ports: `netstat -tl` => `ss -tl`
- Show active connections with PID: `sudo netstat -tup` => `sudo ss -tup`
- View summary statistics: `netstat -s` => `ss -s`


### 5. tcpdump

`tcpdump` is a powerful command-line packet analyzer for Linux. It captures and displays network traffic passing through your system in real time, making it essential for security analysis and troubleshooting.

- Intercepts traffic: It hooks into your network interface to read raw packets.
- Applies filters: It allows you to isolate specific traffic by IP, port, or protocol.
- Saves captures: It exports data into `.pcap` files for analysis in tools like Wireshark.

#### syntax

The standard structure of a tcpdump command is: `tcpdump [options] [filters]`

#### Commands

- `tcpdump -i eth0`: Captures traffic on a specific interface (e.g., eth0).
- `tcpdump -c 10`: Stops automatically after capturing exactly 10 packets.
- `tcpdump -n`: Shows numerical IP addresses and port numbers instead of resolving hostnames.
- `tcpdump -X`: Displays packet content in both Hex and ASCII formats.
- `tcpdump -w output.pcap`: Saves the captured network traffic directly to a file.
- `tcpdump -r output.pcap`: Reads and displays packets from a saved file.

#### Filtering Examples

- `tcpdump host 192.168.1.50`: Captures traffic to or from a specific IP address.
- `tcpdump port 80`: Monitors traffic on a specific port (like HTTP).
- `tcpdump src 10.0.0.5 and dst port 443`: Filters by source IP and destination port.
- `tcpdump icmp`: Isolates only ping (ICMP) traffic.
