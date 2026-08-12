
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
