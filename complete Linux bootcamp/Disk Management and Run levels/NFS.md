
## NFS (Network File System)

Network File System (NFS) lets you share files and directories between Linux computers over a network.

###  Setting Up an NFS Server (Ubuntu/Debian)

Install the server software:

```
sudo apt update
sudo apt install nfs-kernel-server
```

Create the directory you want to share:

```
sudo mkdir -p /var/nfs/general
sudo chown nobody:nogroup /var/nfs/general
```

Export the directory by editing /etc/exports:

`/var/nfs/general  192.168.1.0/24(rw,sync,no_root_squash)`

Apply the configuration and restart the server using instructions from Ubuntu Server documentation:

```
sudo exportfs -a
sudo systemctl restart nfs-kernel-server
```
