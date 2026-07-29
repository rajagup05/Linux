
## linux kernel modules

Linux Kernel Modules (LKMs) are pieces of code that can be dynamically loaded and unloaded into the Linux kernel upon demand to extend its functionality without restarting the operating system. They allow a monolithic system like Linux to remain modular and memory-efficient, functioning as dynamically linkable libraries that execute directly in kernel space with full system privileges.

### 🛠️ Common Use Cases

- Device Drivers: Interfacing the operating system with hardware components like graphics cards, Wi-Fi adapters, and storage devices.
- Filesystem Drivers: Adding the capability to read and write data in specific formats, such as ext4, NTFS, or NFS.
- Network Components: Implementing network protocols, firewall filters (like Netfilter/iptables), or routing rules.

### 💻 Essential CLI Commands

To manage kernel modules, you must have root privileges (using sudo). Compiled modules use the .ko (Kernel Object) file extension and are stored under the /lib/modules/$(uname -r)/ directory.

- `lsmod` — Lists all currently loaded kernel modules and their relationships.
- `modinfo <module_name>` — Displays detailed information, metadata, and parameters for a specific module.
- `modprobe <module_name>` — Intelligently loads or removes a module while resolving all prerequisites and dependencies automatically.
- `insmod <path_to_file.ko>` — Inserts a raw module directly into the kernel, but fails if the target has unresolved dependencies.
- `rmmod <module_name>` — Unloads an active module from memory, provided it is not currently in use.
