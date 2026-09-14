
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

Without allowing loopback interface (lo) and established traffic, internal server processes and internet-bound requests will break: 

```
# Allow local loopback traffic
sudo iptables -A INPUT -i lo -j ACCEPT

# Allow responses from connections you initiated (Stateful Inspection)
sudo iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT
```

- Exposing Specific Services:

```
# Allow SSH (Port 22) from any IP
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT

# Allow Web Traffic (HTTP Port 80 & HTTPS Port 443)
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT
```

- Network Address Translation (NAT) & Port Forwarding:

```
# Forward incoming web traffic on port 80 to an internal server at 192.168.1.50
sudo iptables -t nat -A PREROUTING -p tcp --dport 80 -j DNAT --to-destination 192.168.1.50:80

# Mask traffic leaving an internal network to share a single public IP
sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
```
