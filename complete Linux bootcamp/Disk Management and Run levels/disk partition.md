
## disk partition

In Linux, df and fdisk are fundamental command-line utilities used for storage management. However, they serve completely different purposes: fdisk manages the physical layout of the hard drive (partitions), while df reports on how full the file systems inside those partitions are.

### 1. The df Command: Checking Available Space

The df command tells you how much space is left on your currently active, mounted storage. If a partition exists but isn't mounted to a folder, df will completely ignore it.

- View space in human-readable format (GB, MB): `df -h`
- View space along with the specific filesystem type (like ext4 or xfs): `df -Th`
- Check space on a specific folder or mount point: `df -h /`

### 2. The fdisk Command: Managing Partitions

The fdisk command looks directly at the hardware blocks and partition maps. It allows you to split a single physical drive (like /dev/sda) into multiple independent logical sections (like /dev/sda1, /dev/sda2).

#### Safe Mode: Listing Partitions

- To inspect your hardware and layout without modifying anything, use the -l flag. `sudo fdisk -l`

#### Modifying Mode: Interactive Partitioning

- Running fdisk on a raw block device without the -l flag launches an interactive menu. `sudo fdisk /dev/sdb`
