
## tracing network traffic traceroute

The traceroute command in Linux is a powerful network diagnostic tool used to track the exact path that data packets take from your local machine to a destination host (like a website or an IP address). It lists every router (hop) the packet passes through and measures the time it takes to complete each leg of the journey. 

### Installation

Many modern Linux distributions do not include traceroute by default. You can install it using your system's package manager: 

- Ubuntu / Debian / Mint: `sudo apt update && sudo apt install traceroute`
- CentOS / RHEL / Fedora: `sudo dnf install traceroute`

### Syntax

- To run a basic trace, type traceroute followed by the destination domain name or IP address: `traceroute google.com`

### Reading the Output

The terminal will display a row-by-row mapping of the path: 

- **Hop Number**: The sequential order of the router in the path.
- **Hostname & IP Address**: The identity of the router.
- **Round-Trip Times** (`RTT`): By default, three test packets are sent. The three millisecond (ms) numbers represent how long it took each packet to go to that router and back.
- **Asterisks** (`* * *`): If you see asterisks, it means that specific router did not reply in time. This is usually because a network firewall is configured to block or drop diagnostic probes for security reasons.


### Command Options

You can change how traceroute probes the network by appending options:

- Disable DNS Lookups (`-n`): `traceroute -n google.com`
- Change the Network Protocol (-I or -T):
    - By default, Linux traceroute uses UDP packets. If a corporate firewall is blocking UDP, you can force it to use standard ping or web traffic methods:
        - ICMP (Ping) method: `sudo traceroute -I google.com`
        - TCP (Web) method: `sudo traceroute -T google.com`
- Limit Maximum Hops (`-m`):  `traceroute -m 15 google.com`
- Reduce the Number of Queries (`-q`): `traceroute -q 1 google.com`
