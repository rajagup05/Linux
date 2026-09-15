
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
