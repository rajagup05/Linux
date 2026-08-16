
## NIC or Port binding

### 🧱 NIC Binding (Network Interface Bonding)

NIC bonding aggregates multiple physical interfaces (slaves) into a single logical interface (bond). This provides link aggregation, load balancing, or fault tolerance.

How to Check Your Bond Status: `cat /proc/net/bonding/bond0`

### 🔌 Port Binding (Application Binding)

Port binding occurs when a software program (like Apache, Nginx, or an SSH server) tells the Linux kernel to claim a specific port and listen for incoming traffic on a particular IP address.

#### Types of Binding
