
## firewalls(iptables) in linux

iptables is a command-line utility used to configure the Linux kernel's built-in firewall. It serves as the interface to the Netfilter framework, allowing system administrators to intercept, inspect, and manipulate network traffic. It operates primarily at Layers 3 and 4 of the OSI model (IP addresses, protocols, and ports). 

### Structure: Tables, Chains, and Rules

iptables organizes firewall architecture into a strict hierarchy: Tables contain Chains, Chains contain Rules, and Rules trigger Targets.

#### 🧱 Tables

Tables categorize rules based on the type of decision being made on a network packet. 

- `filter`: The default and most common table. It handles basic traffic filtering (allowing or blocking packets).
- `nat`: Used for Network Address Translation. It rewrites the source or destination IP addresses/ports (e.g., port forwarding or routing local traffic out to the internet).
- `mangle`: Used for specialized packet alteration, such as modifying TTL (Time to Live) fields or changing TOS (Type of Service) headers.
- `raw`: Primarily used to configure exemptions from connection tracking (state tracking).
- `security`: Used for Mandatory Access Control (MAC) networking rules (typically integrated with SELinux). 

#### Chains (The "When")

Chains match the point of arrival or departure of a packet in the network stack: 

- `INPUT`: Processes packets destined for the local system.
- `OUTPUT`: Processes packets generated locally that are leaving the system.
- `FORWARD`: Processes packets routed through the system to another destination (e.g., if the machine acts as a router).
- `PREROUTING`: Alters packets as soon as they arrive on a network interface, before any routing decisions are made.
- `POSTROUTING`: Alters packets right before they leave a network interface. 

#### Targets (The "What")

When a packet matches a rule, it triggers a designated action called a target: 

- `ACCEPT`: Allows the packet to pass through.
- `DROP`: Silently blocks the packet; the sender receives no response.
- `REJECT`: Blocks the packet and explicitly sends an error packet back to the source.
- `LOG`: Records the packet details to system logs (syslog) for auditing without altering its flow.


### Commands

- Viewing Existing Rules: `sudo iptables -L -v -n`
- Establishing a Default Deny Policy:

```
sudo iptables -P INPUT DROP
sudo iptables -P FORWARD DROP
sudo iptables -P OUTPUT ACCEPT
```

- Allowing Vital Infrastructure (Loopback & State Tracking):
