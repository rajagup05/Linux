
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
- Set the partition type or file system use to physical volume (LVM) (or partition type code 8e / 8e00 if doing manual partitioning).

##### Create the Volume Group (VG)

- Combine your selected Physical Volume(s) into a Volume Group.
- Assign a recognizable name to the group, such as vg0 or ubuntu-vg.

##### Create Logical Volumes (LV)

Inside your Volume Group, create individual Logical Volumes for your mount points:

- **Root (/)**: Allocate the majority of your space or a dedicated size (e.g., 20GB+).
- **Swap**: Allocate virtual memory space matching your RAM needs.
- **Home (/home)** or **Var (/var)**: Optional separate volumes to isolate user data or logs.

Assign the desired file system type (such as ext4 or xfs) and mount points to each Logical Volume.

##### Complete the Installation

- Proceed with the rest of the installation. The installer automatically formats the logical volumes, mounts them, and configures the bootloader and initramfs to recognize the LVM structure upon reboot.
