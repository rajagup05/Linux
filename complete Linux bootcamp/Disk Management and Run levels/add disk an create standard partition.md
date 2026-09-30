
## add disk and create standard partition

### Step 1: Detect the New Disk

First, identify the device name assigned to your newly added hard disk. Run the following command:

`sudo fdisk -l`

### Step 2: Create a Standard Partition with fdisk

Open the interactive fdisk menu for your new drive:

`sudo fdisk /dev/sdb`
