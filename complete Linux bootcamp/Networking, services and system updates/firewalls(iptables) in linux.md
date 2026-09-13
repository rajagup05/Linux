
## firewalls(iptables) in linux

iptables is a command-line utility used to configure the Linux kernel's built-in firewall. It serves as the interface to the Netfilter framework, allowing system administrators to intercept, inspect, and manipulate network traffic. It operates primarily at Layers 3 and 4 of the OSI model (IP addresses, protocols, and ports). 

### 1. Structure: Tables, Chains, and Rules

iptables organizes firewall architecture into a strict hierarchy: Tables contain Chains, Chains contain Rules, and Rules trigger Targets.

#### 🧱 Tables

Tables categorize rules based on the type of decision being made on a network packet. 

- `filter`: The default and most common table. It handles basic traffic filtering (allowing or blocking packets).
- `nat`: Used for Network Address Translation. It rewrites the source or destination IP addresses/ports (e.g., port forwarding or routing local traffic out to the internet).
- `mangle`: Used for specialized packet alteration, such as modifying TTL (Time to Live) fields or changing TOS (Type of Service) headers.
- `raw`: Primarily used to configure exemptions from connection tracking (state tracking).
- `security`: Used for Mandatory Access Control (MAC) networking rules (typically integrated with SELinux). 
