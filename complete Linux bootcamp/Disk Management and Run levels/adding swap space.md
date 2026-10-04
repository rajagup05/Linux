
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
