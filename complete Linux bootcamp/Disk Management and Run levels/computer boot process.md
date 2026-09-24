
## computer boot process

The Linux booting process moves through five main stages from the moment you turn on the power until you see a login screen.

### 1. BIOS / UEFI (Firmware)

- The computer turns on and runs a POST (Power-On Self-Test) to check hardware like RAM and the CPU.
- The system searches for a valid boot device (hard drive, USB, or CD) using the Basic Input/Output System (BIOS) or modern UEFI.
- It finds and reads the first boot sector—traditionally the Master Boot Record (MBR) or the EFI system partition—to hand control over to the bootloader.

### 2. Boot Loader (GRUB)

- The Grand Unified Bootloader (GRUB) starts up and usually shows a menu letting you choose which operating system or kernel to launch.
- GRUB loads the compressed Linux kernel and the temporary root file system (initramfs) straight into the computer's memory (RAM).

### 3. Kernel Initialization

- The kernel decompresses itself and takes full control of the computer's hardware and memory.
- It runs the temporary file system (initramfs) to find, load, and initialize necessary device drivers and hardware modules.
- The kernel mounts the real local root file system.

### 4. Init System (systemd)

- The kernel starts the very first user-space program, traditionally called init, which has a Process ID (PID) of 1.
- 
