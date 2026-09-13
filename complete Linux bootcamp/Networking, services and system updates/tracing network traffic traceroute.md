
## tracing network traffic traceroute

The traceroute command in Linux is a powerful network diagnostic tool used to track the exact path that data packets take from your local machine to a destination host (like a website or an IP address). It lists every router (hop) the packet passes through and measures the time it takes to complete each leg of the journey. 

### Installation

Many modern Linux distributions do not include traceroute by default. You can install it using your system's package manager: 

- Ubuntu / Debian / Mint: `sudo apt update && sudo apt install traceroute`
- CentOS / RHEL / Fedora: `sudo dnf install traceroute`
