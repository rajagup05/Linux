
## add disk and create new LVM partition (pvcreate, vgcreate, lgcreate)

To add a new disk and configure it using LVM (Logical Volume Manager), follow these five steps. Replace /dev/sdb with the actual identifier of your new storage device. All commands require root or sudo privileges.

### Step 1: Identify the New Disk

Run the following command to find the name of your newly added raw disk (e.g., /dev/sdb, /dev/nvme1n1):

`sudo fdisk -l`

### Step 2: Initialize the Physical Volume (pvcreate)

Initialize the raw disk (or a partition) as an LVM Physical Volume (PV):

`sudo pvcreate /dev/sdb`
