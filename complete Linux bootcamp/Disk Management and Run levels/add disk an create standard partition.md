
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
- Verify it is working using df: `df -h /mnt/mydata`

### Step 5: Make it Permanent (Optional)

If you reboot your system right now, the disk will unmount. To ensure it mounts automatically at every boot, add it to your filesystem table (/etc/fstab).

- Find the UUID (Unique ID) of your new partition: `sudo blkid /dev/sdb1`
- Open the configuration file in a text editor: `sudo nano /etc/fstab`
- Add the following new line at the bottom of the file (replace the example UUID with yours): `UUID=your-uuid-here  /mnt/mydata  ext4  defaults  0  2`
- Save and exit (In Nano: Press `Ctrl+O`, `Enter`, then `Ctrl+X`).
