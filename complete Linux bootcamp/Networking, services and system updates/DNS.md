
## DNS

In Linux, the Domain Name System (DNS) translates human-readable domain names into numeric IP addresses. Configuration relies on core files like /etc/hosts for static mapping, /etc/resolv.conf to designate active name servers, and package tools like BIND (Berkeley Internet Name Domain) to host local servers.

- `/etc/hosts`: Contains static local IP-to-hostname mappings, checked first before querying external DNS.
- `/etc/resolv.conf`: Lists active resolver name servers (e.g., nameserver 8.8.8.8) used by the system.
- `/etc/nsswitch.conf`: Sets the decision order for lookups between local files and network DNS.
- `/etc/systemd/resolved.conf`: Manages network name resolution behavior on modern systemd-based distros.

- `dig domain.com`: Performs detailed DNS lookups and troubleshooting diagnostics.
- `nslookup domain.com`: Queries name server mappings interactively or directly.
- `host domain.com`: Provides a quick, simple IP lookup for a host.
- `systemctl restart systemd-resolved`: Restarts the local resolver service after configuration updates.
