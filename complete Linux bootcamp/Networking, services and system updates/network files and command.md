
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

