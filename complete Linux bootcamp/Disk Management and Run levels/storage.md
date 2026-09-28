
## storage

Linux local storage and networked architectures like DAS, NAS, and SAN differ primarily in how storage hardware physically connects to a system and the level at which data is accessed (block vs. file).

### Linux Local Storage and DAS (Direct-Attached Storage)

- **Direct-Attached Storage (DAS)**: Storage hardware that connects physically and directly to a single host computer or server without passing through a local network switch. Examples include internal NVMe/SATA drives, USB external hard drives, or hardware connected via a dedicated Host Bus Adapter (HBA).
- **Linux Perspective**: In Linux, DAS devices appear as raw block devices (e.g., /dev/sda, /dev/nvme0n1). The operating system must format these blocks with a local file system (such as ext4 or XFS) and mount them directly.
- **Pros & Cons**: Offers high speed, low latency, and simple setup, but cannot be easily shared with other independent servers.

### NAS (Network-Attached Storage)

