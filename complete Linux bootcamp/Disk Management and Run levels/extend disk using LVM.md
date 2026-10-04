
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

#### Scenario B: Adding a New Disk (e.g., /dev/sdb)

- Initialize the new disk or partition as a Physical Volume: `sudo pvcreate /dev/sdb`
- Extend your existing Volume Group by adding the new physical volume: `sudo vgextend <volume_group_name> /dev/sdb`

### Step 3: Extend the Logical Volume

- Extend the Logical Volume to use the newly available free space. You can use -l +100%FREE to consume all available free space in the volume group: `sudo lvextend -l +100%FREE /dev/<volume_group_name>/<logical_volume_name>`

### Step 4: Resize the Filesystem

- If you did not use the -r flag in the previous step, resize your filesystem manually depending on the filesystem type:
  - For EXT4 filesystems: `sudo resize2fs /dev/<volume_group_name>/<logical_volume_name>`
  - For XFS filesystems: `sudo xfs_growfs /mount_point_path`

### Step 5: Verify the Changes

Run df -h again to confirm that the new storage capacity is successfully assigned and visible.

