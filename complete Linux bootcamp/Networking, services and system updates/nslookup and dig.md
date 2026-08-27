
## nslookup and dig

nslookup and dig are the two primary Linux command-line utilities used to query the Domain Name System (DNS) and troubleshoot network connectivity issues. While they accomplish the same core goal, dig (Domain Information Groper) is highly detailed, flexible, and preferred for automation, whereas nslookup offers clean, basic formatting and an interactive query mode.

### 🔍 1. How to Use the dig Command

dig returns highly granular information including query response times, TTL (Time to Live) data, and authority flags.

- Standard Domain Lookup: `dig google.com` (Fetches the target domain's IP addresses and standard records.)
- Get a Clean, Short Response: `dig google.com +short` (Suppresses the technical headers to return only the IP addresses. Excellent for scripting.)
- Query a Specific Record Type: `dig google.com MX`(Look up specific mail servers (MX), nameservers (NS), or text records (TXT).)
- Query a Specific DNS Server: `dig @8.8.8.8 google.com` (Queries a specific nameserver (like Google's public 8.8.8.8) directly, bypassing your local network settings.)
- Trace the Full DNS Path: `dig google.com +trace` (Follows the query path step-by-step from Root servers down to the Authoritative nameserver.)

### 🔍 2. How to Use the nslookup Command

nslookup strips away the systemic noise, giving you quick answers. It can be used directly from the terminal or inside an exclusive shell.

- Standard Domain Lookup: `nslookup google.com`
- Reverse Lookup (IP to Domain): `nslookup 8.8.8.8` (Pass a raw IP address directly to figure out what domain maps to it.)
- Query a Specific DNS Server: `nslookup google.com 8.8.8.8`
- Using Interactive Mode: (Typing nslookup without arguments locks you into a targeted prompt. From there, you can change settings dynamically without retyping commands:)

```
nslookup
> set type=MX
> google.com
> server 1.1.1.1
> google.com
> exit
```
