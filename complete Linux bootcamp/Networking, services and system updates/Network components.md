
## Network Components

### 1. IP

The ip command (part of the iproute2 suite) is the standard Linux utility used to configure and view network interfaces, IP addresses, routing, and policy tables, completely replacing the obsolete ifconfig tool.

- `ip addr show`: Displays all network interfaces, their assigned IPv4/IPv6 addresses, and operational status.
- `ip addr add 192.168.1.50/24 dev eth0`: Assigns a static IP address to a specific network interface.
- `ip link set eth0 up`: Enables a network interface (change up to down to disable it).
- `ip route add default via 192.168.1.1`: Configures the default gateway route for internet traffic.

### 2. subnet mask

A subnet mask hides (masks) parts of an IP address to divide it into two parts: the network address and the host address. It tells computers which other devices are on the same local network and which ones require a router to reach.

#### How It Works (The Analogy)

Think of an IP address like a phone number: `(555) 019-2834`

- The area code `(555)` is the network. It routes the call to the right town.
- The remaining digits `019-2834` represent the specific host (the phone in a house).

The subnet mask acts as a blueprint that tells the system exactly where the area code ends and the unique phone number begins.

#### The Binary Mechanism

Computers read IP addresses and subnet masks in binary (1s and 0s).

- **1s** in the subnet mask represent the **Network**. These bits are locked.
- **0s** in the subnet mask represent the **Host**. These bits can change to assign numbers to devices.

how a standard `255.255.255.0` mask splits the IP address `192.168.1.50`:

    Component    Dotted Decimal    Binary Equivalent    Purpose
    
    IP Address    192.168.1.50    11000000.10101000.00000001.00110010    Device Identity
    Subnet Mask    255.255.255.0    11111111.11111111.11111111.00000000    Network Filter
    Network Portion    192.168.1.X    11000000.10101000.00000001.00000000    The "Street Name"
    Host Portion    X.X.X.50    00000000.00000000.00000000.00110010    The "House Number"

#### CIDR Notation (The Shorthand)

Writing out `255.255.255.0` is tedious. Instead, network administrators use CIDR (Classless Inter-Domain Routing) notation, which simply counts the number of `1` bits in the mask.

- Because `255.255.255.0` has twenty-four 1 bits, it is written as `/24`.
- `192.168.1.50` with a mask of `255.255.255.0`

#### The Two Reserved Addresses

In any subnet, you cannot use the very first or the very last IP address for a device:

- Network ID (First IP): Identifies the network itself (e.g., `192.168.1.0`).
- Broadcast Address (Last IP): Used to send data to all hosts simultaneously (e.g., `192.168.1.255`).


### 3. Gateway

A gateway (specifically a default gateway) is a network node that connects two different networks using different protocols or address ranges. It acts as an exit point for data packets bound for destinations outside the local subnet, routing local network traffic to the broader internet.

#### How It Works (The Analogy)

Think of your local network as an office building and a gateway as the exit door.

- If you want to talk to a coworker in the same building (local network), you walk directly to their desk.
- If you want to mail a letter to someone in another city (external network/internet), you must take it to the front exit door (gateway) so it can be sent out into the world.

Without a gateway configured, your computer can talk to other local devices but cannot access websites, servers, or any external internet resources.

#### How a Linux System Processes the Gateway

When you request a website (e.g., an external IP like 93.184.215.14), the Linux kernel performs a calculation using its routing table:

- Local Check: It checks if the destination IP is inside your subnet mask.
- The Exit Plan: Since the destination is external, the kernel sends the packet directly to the MAC address of the Default Gateway (usually your router's IP, like 192.168.1.1).
- The Hand-off: The router receives the packet and passes it along to your Internet Service Provider (ISP).

#### Managing Gateways in Linux via CLI

- View your gateway: `ip route show` (Output example: default via 192.168.1.1 dev eth0 proto dhcp src 192.168.1.50 (This shows 192.168.1.1 is your gateway))
- Add a default gateway manually: `sudo ip route add default via 192.168.1.1 dev eth0`
- Delete a default gateway: `sudo ip route del default via 192.168.1.1 dev eth0`

### 4. static and DHCP ip

The core difference between a Static and a DHCP IP address comes down to who assigns the address and how long it stays the same

        Feature    Static IP    DHCP IP    
        
        Assignment         Manually typed by an administrator            Assigned automatically by a server/router
        Persistence        Permanent (never changes unless edited)       Temporary (changes when the "lease" expires)
        Risk of Conflict   High (if you typo an address already in use)  None (the server tracks who has what)
        Best Used For      Servers, printers, NAS, gateways              Laptops, phones, desktop workstations

#### Static IP (Manual)

A static IP is configured locally on the device. It bypasses the router's automatic allocation entirely.

- The Benefit: The address is completely predictable. If your file server is at 192.168.1.10, it will stay at 192.168.1.10
- The Downside: High administrative overhead. If you move your laptop to a coffee shop network, your manually typed static IP will cause a total loss of internet connection until you change it back.

#### DHCP IP (Dynamic Host Configuration Protocol)

DHCP is a network protocol that automates IP configuration. When a device boots up, it broadcasts a request ("Is there a DHCP server here?"). The server (usually your router) leases it an IP, subnet mask, and gateway.

- The Benefit: Total plug-and-play simplicity. You can move between home, work, and public Wi-Fi networks without ever touching your network settings.
- The Downside: The IP can change. If you host a local website or gaming server, your friends might lose access tomorrow if your router assigns your computer a different address.



### 5. INTERFACE

In Linux, a network interface is the software boundary between the operating system kernel and a network. It acts as the gateway that allows the system to send and receive data packets, whether using physical hardware or entirely virtual connections.

#### How Interfaces Work

Unlike devices like disks, network interfaces do not appear as files in the /dev directory. Instead, the kernel assigns them unique names (like eth0 or wlan0) and manages them via standard system configuration tools. Every interface must have a layer 2 hardware address (MAC address) and usually a layer 3 protocol configuration (IPv4 or IPv6 address) to process network traffic.

#### Types of Interfaces

- Physical Interfaces: Hardware cards like Ethernet (`eth0`, `enp3s0`) or Wi-Fi (`wlan0`) that connect to actual cables or wireless signals.
- Loopback Interface (lo): A special, purely virtual interface used by the system to talk to itself. It always uses the IP address `127.0.0.1`.
- Virtual Interfaces: Software-created interfaces with no dedicated physical hardware, such as:
  - Bridges (br0): Virtual switches that link multiple interfaces together.
  - VETH Pairs: Virtual Ethernet cables used to connect isolated container environments.

#### Checking Interface Status

You can view and manage interfaces using the modern ip tool from the iproute2 package:

```
# View all active and inactive interfaces on the system
ip link show

# View detailed IP address assignments for each interface
ip address show
```

### 6. INTERFACE MAC

In Linux, an interface MAC (Media Access Control) address is a unique 48-bit (6-byte) physical hardware identifier assigned to a network interface card (NIC). While IP addresses route data across different networks, MAC addresses deliver data packets between devices on the same local network segment (Layer 2 of the OSI model).

#### How MAC Addresses Work in Linux

- Hardware vs. Software: The physical MAC address is burned into the NIC by the manufacturer (the Burned-In Address or BIA). However, during boot, the Linux kernel reads this value into system memory, allowing users to temporarily override or "spoof" it using software commands.
- Format: It is written as six groups of two hexadecimal digits separated by colons (e.g., `00:1a:2b:3c:4d:5e`).
- The First 3 Bytes: Known as the OUI (Organizationally Unique Identifier), these identify the manufacturer of the network card (e.g., Intel, Realtek).
- The Last 3 Bytes: A unique serial number assigned by the manufacturer to that specific device.
