
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

Look for INTERFACESv4 and assign your network card name (for example, eth0 or enp0s3):

`INTERFACESv4="enp0s3"`

### 3. Edit the DHCP Configuration File

Open the main configuration file to set up your IP address range, gateway, and DNS servers:

`sudo nano /etc/dhcp/dhcpd.conf`

Add or uncomment a subnet declaration matching your network layout:
