
## DHCP server

You can set up a DHCP server on a Linux system by installing the traditional ISC DHCP Server package (isc-dhcp-server) and defining your subnet pools.

### 1. Install the DHCP Server

On Debian or Ubuntu systems, run the package update and installation commands in your terminal:

```
sudo apt update
sudo apt install isc-dhcp-server
```

### 2. Configure the Network Interface

Define which network interface the server will use to broadcast IP addresses by editing the default configuration file:

```
sudo nano /etc/default/isc-dhcp-server
```
