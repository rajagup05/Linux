
## nftables

nftables is the modern packet classification and filtering framework in Linux. It serves as the official successor to the legacy {ip,ip6,arp,eb}tables (collectively known as iptables) infrastructure. 

Managed via the user-space command-line tool nft, it interacts directly with the Linux kernel's nf_tables subsystem to provide robust firewalling, Network Address Translation (NAT), and packet mangling. 

### Why nftables Replaced iptables

For over a decade, iptables was the standard Linux firewall. However, its architecture had fundamental limitations that nftables was designed to solve: 

- **Unified Framework**: Instead of using separate utilities for different protocols (iptables for IPv4, ip6tables for IPv6, arptables, and ebtables), nftables replaces them all with a single tool (nft).
- **The inet Dual-Stack Family**: You can write a single rule that filters both IPv4 and IPv6 traffic simultaneously using the inet family.
- **No Predefined Chains**: Unlike iptables, which creates default chains (INPUT, OUTPUT, FORWARD) even if you don't use them, nftables starts completely empty. This eliminates unnecessary kernel overhead for unused paths.
- **Atomic Transactions**: You can update or replace entire complex rule sets in-place as a single atomic operation. Your firewall configuration changes instantly without risking packet leaks or requiring full restarts.
- **Cleaner Syntax**: The syntax is more concise and reads similarly to tcpdump or OpenBSD's pf. 

nftables organizes rules into a strict hierarchy: **Tables ➔ Chains ➔ Rules**.

- **Tables**: Containers for chains. Each table must target a specific networking family (e.g., ip, ip6, inet, arp, bridge).
- **Chains**: Containers for rules.
  - Base chains hook directly into Linux kernel network flows (like input, forward, or output).
  - Regular chains act as custom subroutines you can jump into from a base chain.
- **Rules**: The specific expressions that match packets and trigger actions (e.g., accept, drop, reject). 

### Examples

-  Create a Table and a Base Chain:

```
# Create an 'inet' table named 'filter'
nft add table inet filter

# Create an 'input' chain that hooks into the incoming packet stream
nft add chain inet filter input { type filter hook input priority 0 \; policy accept \; }
```

-  Add Rules:

```
# Allow incoming SSH (port 22) and HTTP/HTTPS traffic
nft add rule inet filter input tcp dport 22 accept
nft add rule inet filter input tcp dport { 80, 443 } accept

# Drop everything else (if changing policy to drop)
nft add rule inet filter input drop
```

- Manage the Ruleset:

```
# List the current ruleset with line handles (useful for deleting)
nft list ruleset -a

# Delete a specific rule using its handle ID (e.g., handle 4)
nft delete rule inet filter input handle 4

# Flush (clear) all current rules
nft flush ruleset
```

### Configuration Files

- In most distributions like Debian, Ubuntu, or RHEL, your permanent configuration file is located at /etc/nftables.conf. You can save your active rules directly into it to persist across reboots: `nft list ruleset > /etc/nftables.conf`
