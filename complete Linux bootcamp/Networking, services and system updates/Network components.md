
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


### Gateway

A gateway (specifically a default gateway) is a network node that connects two different networks using different protocols or address ranges. It acts as an exit point for data packets bound for destinations outside the local subnet, routing local network traffic to the broader internet.

#### How It Works (The Analogy)

Think of your local network as an office building and a gateway as the exit door.

- If you want to talk to a coworker in the same building (local network), you walk directly to their desk.
- If you want to mail a letter to someone in another city (external network/internet), you must take it to the front exit door (gateway) so it can be sent out into the world.

Without a gateway configured, your computer can talk to other local devices but cannot access websites, servers, or any external internet resources.

#### How a Linux System Processes the Gateway

When you request a website (e.g., an external IP like 93.184.215.14), the Linux kernel performs a calculation using its routing table:

