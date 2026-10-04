
## extend disk using LVM

To extend a disk using LVM in Linux, you need to resize the partition/disk, resize the physical volume, extend the volume group and logical volume, and finally grow the filesystem.

### Step 1: Check Current Storage and LVM Layout

- Run `df -h` to see current disk usage and mount points.
- Run `lsblk` or `vgs` and `lvs` to identify your Volume Group (VG) and Logical Volume (LV) names.

### Step 2: Extend the Partition or Add a New Disk

Choose Scenario A if you resized an existing virtual disk/partition, or Scenario B if you attached a brand-new physical or virtual disk.

#### Scenario A: Resizing an Existing Partition (e.g., /dev/sda3)

- Rescan your partition table or resize the partition using a tool like growpart or parted: `sudo growpart /dev/sda 3`
- Resize the LVM Physical Volume (PV) to recognize the new partition size: `sudo pvresize /dev/sda3`
