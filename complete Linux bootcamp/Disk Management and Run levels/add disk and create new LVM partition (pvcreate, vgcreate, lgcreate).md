
## add disk and create new LVM partition (pvcreate, vgcreate, lgcreate)

To add a new disk and configure it using LVM (Logical Volume Manager), follow these five steps. Replace /dev/sdb with the actual identifier of your new storage device. All commands require root or sudo privileges.

### Step 1: Identify the New Disk

Run the following command to find the name of your newly added raw disk (e.g., /dev/sdb, /dev/nvme1n1):

`sudo fdisk -l`

### Step 2: Initialize the Physical Volume (pvcreate)

Initialize the raw disk (or a partition) as an LVM Physical Volume (PV):

`sudo pvcreate /dev/sdb`

### Step 3: Create a Volume Group (vgcreate)

Combine your physical volume into a new Volume Group (VG). Replace my_vg with your preferred group name:

`sudo vgcreate my_vg /dev/sdb`

### Step 4: Create a Logical Volume (lvcreate)

Allocate storage from your Volume Group to create a Logical Volume (LV). Replace my_lv with your preferred volume name:

#### Option A: Allocate by specific size (e.g., 20 Gigabytes):

`sudo lvcreate -L 20G -n my_lv my_vg`

#### Option B: Allocate 100% of the remaining free space in the VG:

`sudo lvcreate -l 100%FREE -n my_lv my_vg`

### Step 5: Format and Mount the Volume

To make the new storage usable, format it with a filesystem and attach it to your directory tree.

- Format with a filesystem (such as Ext4 or XFS): `sudo mkfs.ext4 /dev/my_vg/my_lv`
- Create a mount point directory: `sudo mkdir -p /mnt/my_storage`
- Mount the volume manually: `sudo mount /dev/my_vg/my_lv /mnt/my_storage`
