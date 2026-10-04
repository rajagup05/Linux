
## adding swap space

### Step 1: Check your current swap status

Before starting, check if your system already has an active swap space: `sudo swapon --show` (If the output is empty, your system currently has no active swap).

### Step 2: Allocate memory space for the swap file

Create a file of the desired size. Using fallocate is the fastest method. For a 2 GB file, run: `sudo fallocate -l 2G /swapfile`

