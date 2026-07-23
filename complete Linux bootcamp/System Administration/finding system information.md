
## finding system information uname dmidecode

In Linux, you can find a wealth of system details by combining uname for operating system and kernel data, and dmidecode for low-level hardware specifications.

### 🐧 Operating System and Kernel Information: uname

- `uname -a`: Prints all available system information in one line.
- `uname -r`: Displays the active kernel release version.
- `uname -m`: Shows the machine's CPU architecture (e.g., x86_64).
- `uname -n`: Outputs the network node hostname.
- `uname -s`: Prints the kernel name (usually Linux).

### 🛠️ Hardware Component Information: dmidecode

The dmidecode command safely dumps hardware configurations directly from the BIOS/UEFI without probing physical components. Because its raw output is massive, you should always target specific hardware types using the -t (or --type) switch:

- `sudo dmidecode -t system`: Identifies system information including the manufacturer, product name, and serial number.
