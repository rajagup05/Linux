
## linux kernel modules

Linux Kernel Modules (LKMs) are pieces of code that can be dynamically loaded and unloaded into the Linux kernel upon demand to extend its functionality without restarting the operating system. They allow a monolithic system like Linux to remain modular and memory-efficient, functioning as dynamically linkable libraries that execute directly in kernel space with full system privileges.

### 🛠️ Common Use Cases

- Device Drivers: Interfacing the operating system with hardware components like graphics cards, Wi-Fi adapters, and storage devices.
- Filesystem Drivers: Adding the capability to read and write data in specific formats, such as ext4, NTFS, or NFS.
- Network Components: Implementing network protocols, firewall filters (like Netfilter/iptables), or routing rules.
