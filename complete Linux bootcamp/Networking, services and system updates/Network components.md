
## Network Components

### 1. IP

The ip command (part of the iproute2 suite) is the standard Linux utility used to configure and view network interfaces, IP addresses, routing, and policy tables, completely replacing the obsolete ifconfig tool.

- `ip addr show`: Displays all network interfaces, their assigned IPv4/IPv6 addresses, and operational status.
- `ip addr add 192.168.1.50/24 dev eth0`: Assigns a static IP address to a specific network interface.
- `ip link set eth0 up`: Enables a network interface (change up to down to disable it).
- `ip route add default via 192.168.1.1`: Configures the default gateway route for internet traffic.
