
## linux boot process

The Linux booting process is a sequential 5-stage startup sequence that transitions a computer from a powered-off state to a fully operational environment.

### 1. BIOS / UEFI (Firmware Stage)

- Power-On Self-Test (POST): The system powers on and the motherboard firmware (BIOS or UEFI) runs diagnostics to verify essential hardware like RAM, CPU, and storage.
- Boot Device Search: The firmware scans configured drives (SSD, HDD, USB, or network) for boot records.

### 2. MBR / GPT (Master Boot Record Stage)

- Finding the Bootloader: On older systems, the BIOS reads the first 512-byte sector of the bootable disk (MBR) to find primary boot code. Modern systems use UEFI with GPT partition tables instead.
- Handing Over Control: Control is transferred to the primary boot program to locate the secondary loader.

### 3. GRUB (Bootloader Stage)

- Grand Unified Bootloader: GRUB displays the boot menu, allowing users to pick an operating system or recovery kernel.
- Loading the Kernel: GRUB reads its configuration file and loads the compressed Linux kernel image (vmlinuz) and initial RAM filesystem (initramfs) into memory before exiting.

### 4. Kernel and Initramfs (Kernel Stage)

- Hardware Initialization: The Linux kernel decompresses itself, examines the system hardware, and loads necessary device drivers.
- Mounting the Root File System: It mounts a temporary root file system (initramfs) to load essential drivers, then switches over to the real physical root file system.

### 5. Init / Systemd (Initialization Stage)

- Process ID 1: The kernel launches the first user-space program (systemd) with a Process ID (PID) of 1.
- Target States: systemd reads target configurations to launch background services, network settings, and finally the login prompt or graphical desktop manager.
