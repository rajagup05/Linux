
## NIC information

To check Network Interface Card (NIC) and interface information in Linux, use the modern ip link or ip addr commands, hardware detail tools like lshw -C network or lspci, and ethtool for link speeds.

### Listing Interfaces and IP Details

- `ip link show`: Lists all network devices and their states (UP/DOWN).
- `ip addr`: Displays IP addresses (IPv4/IPv6) and MAC addresses assigned to each card.
- `ifconfig -a`: Older legacy tool showing active interface configurations and packet statistics.

- `ethtool <interface_name>`: Views active link speed, duplex mode, and capabilities (requires root/sudo for full details).
