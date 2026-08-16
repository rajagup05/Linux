
## NIC or Port binding

### 🧱 NIC Binding (Network Interface Bonding)

NIC bonding aggregates multiple physical interfaces (slaves) into a single logical interface (bond). This provides link aggregation, load balancing, or fault tolerance.

To Check Your Bond Status: `cat /proc/net/bonding/bond0`

### 🔌 Port Binding (Application Binding)

Port binding occurs when a software program (like Apache, Nginx, or an SSH server) tells the Linux kernel to claim a specific port and listen for incoming traffic on a particular IP address.

#### Types of Binding

- **Global Bind** (`0.0.0.0`): The service listens on all available network interfaces and IP addresses assigned to the machine.
- **Local Bind** (`127.0.0.1`): The service listens only on the localhost loopback adapter. It is completely inaccessible from the outside network.
- **Specific Bind** (`192.168.1.50`): The service binds to a single designated NIC IP, entirely ignoring traffic sent to other network interfaces.

 To View Active Port Bindings: `ss -tulnp`
