
## storage

Linux local storage and networked architectures like DAS, NAS, and SAN differ primarily in how storage hardware physically connects to a system and the level at which data is accessed (block vs. file).

### Linux Local Storage and DAS (Direct-Attached Storage)

- **Direct-Attached Storage (DAS)**: Storage hardware that connects physically and directly to a single host computer or server without passing through a local network switch. Examples include internal NVMe/SATA drives, USB external hard drives, or hardware connected via a dedicated Host Bus Adapter (HBA).
- **Linux Perspective**: In Linux, DAS devices appear as raw block devices (e.g., /dev/sda, /dev/nvme0n1). The operating system must format these blocks with a local file system (such as ext4 or XFS) and mount them directly.
- **Pros & Cons**: Offers high speed, low latency, and simple setup, but cannot be easily shared with other independent servers.

### NAS (Network-Attached Storage)

- **Definition**: A dedicated file-level storage device connected to a standard Ethernet/IP network that serves shared folders to clients.
- **Linux Perspective**: The NAS appliance manages its own internal file system and exposes it over the network. Linux mounts these remote shares using file-level network protocols—most commonly NFS (Network File System) for Linux/Unix environments or SMB/CIFS for cross-platform sharing.
- **Pros & Cons**: Highly cost-effective and simple for multi-user file collaboration, but file-locking overhead makes it less suitable for high-transaction databases.

### SAN (Storage Area Network)

- **Definition**: A specialized, high-speed dedicated network (using Fibre Channel or iSCSI over Ethernet) that connects servers to centralized block-level storage arrays.
- **Linux Perspective**: To a Linux kernel, a SAN LUN (Logical Unit Number) appears identical to a local physical hard disk (as a block device under /dev/mapper/ or /dev/sd*). Linux must create its own file system (ext4, XFS, or clustered file systems like OCFS2) directly on top of the block device.
- **Pros & Cons**: Delivers elite performance, low latency, and deep virtualization/database support, but comes with high complexity and expensive specialized hardware requirements.

