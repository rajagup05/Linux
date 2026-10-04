
## adding swap space

### Step 1: Check your current swap status

Before starting, check if your system already has an active swap space: `sudo swapon --show` (If the output is empty, your system currently has no active swap).

### Step 2: Allocate memory space for the swap file

Create a file of the desired size. Using fallocate is the fastest method. For a 2 GB file, run: `sudo fallocate -l 2G /swapfile`

### Step 3: Secure the swap file

For security reasons, only the root user should be allowed to read or write to this file. Lock down its permissions: `sudo chmod 600 /swapfile`

### Step 4: Format the file as swap

Set up the file to serve as a Linux swap area: `sudo mkswap /swapfile`

### Step 5: Activate the swap file

Tell the Linux kernel to start using your newly created file for virtual memory: `sudo swapon /swapfile`

### Step 6: Make the swap permanent (Survivable through Reboots)

By default, the swap file will turn off when you reboot the computer. To make it permanent, open the filesystem configuration file (/etc/fstab) in a text editor: `sudo nano /etc/fstab`

Move to the bottom of the file and add the following line: `/swapfile none swap defaults 0 0`

Save and exit the text editor (in Nano, press `Ctrl+O`, `Enter`, then `Ctrl+X`).

### Step 7: Verify it works

Run either of these commands to verify that your swap memory is active and has increased:

`sudo swapon --show` or `free -h`
