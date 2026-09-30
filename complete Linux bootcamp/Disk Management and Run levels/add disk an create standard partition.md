
## add disk and create standard partition

### Step 1: Detect the New Disk

First, identify the device name assigned to your newly added hard disk. Run the following command:

`sudo fdisk -l`

### Step 2: Create a Standard Partition with fdisk

Open the interactive fdisk menu for your new drive:

`sudo fdisk /dev/sdb`

### Step 3: Format the New Partition

Now that the partition (/dev/sdb1) is created, you must format it with a Linux filesystem (like ext4) so it can store data:

`sudo mkfs.ext4 /dev/sdb1`

### Step 4: Mount the Partition

To use the disk, you need to attach (mount) it to a folder in your directory tree.

- Create a directory to serve as your mount point: `sudo mkdir -p /mnt/mydata`
- Mount the partition to that directory: `sudo mount /dev/sdb1 /mnt/mydata`
