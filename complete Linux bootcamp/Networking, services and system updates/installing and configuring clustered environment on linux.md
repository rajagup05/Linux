
## installing and configuring clustered environment on linux

Setting up a High Availability (HA) cluster on Linux ensures that if one server (node) fails, another instantly takes over to keep your applications running without downtime.

This guide outlines how to build a standard production-ready Pacemaker and Corosync HA cluster on RHEL/CentOS/Rocky Linux or Ubuntu/Debian systems.

### Step 1: Meet the Prerequisites

Before installing packages, configure your nodes (this example uses a two-node architecture). Run these commands on all nodes:

- **Set Hostnames**: Ensure each node has a unique hostname. `sudo hostnamectl set-hostname node1.example.com`
- **Update the Hosts File**: Open /etc/hosts and map the IP addresses of all cluster members.

```
192.168.1.10 node1.example.com node1
192.168.1.11 node2.example.com node2
```

- **Synchronize Time**: Clusters rely on exact timing to prevent data corruption. Ensure chronyd or NTP is running: `sudo systemctl enable --now chronyd`
