
## LVM configuration during installation

Configuring Logical Volume Manager (LVM) during a Linux installation allows you to resize partitions dynamically and manage storage efficiently without reformatting.

### LVM Core Concepts

- **Physical Volume (PV)**: Your raw disk or partition (e.g., /dev/sdb1) initialized for LVM.
- **Volume Group (VG)**: A storage pool combining one or more Physical Volumes.
- **Logical Volume (LV)**: Virtual partitions carved out of a Volume Group where filesystems are created.

#### Installation

##### Select LVM Option in the Installer

- During the disk partitioning step of your Linux distribution (like Ubuntu, Fedora, or RHEL), choose the Advanced Partitioning or look for an option like "Use LVM with the new installation" or "Set up LVM".
- Some installers also offer an Encrypted LVM option for added security.

##### Create Physical Volumes (PV)

- Select your target unpartitioned disk or free space (e.g., /dev/sdb).
- 
