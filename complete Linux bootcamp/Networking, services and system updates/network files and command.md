
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

