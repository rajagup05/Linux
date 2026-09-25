
## linux boot process

The Linux booting process is a sequential 5-stage startup sequence that transitions a computer from a powered-off state to a fully operational environment.

### 1. BIOS / UEFI (Firmware Stage)

- Power-On Self-Test (POST): The system powers on and the motherboard firmware (BIOS or UEFI) runs diagnostics to verify essential hardware like RAM, CPU, and storage.
- Boot Device Search: The firmware scans configured drives (SSD, HDD, USB, or network) for boot records.

### 2. MBR / GPT (Master Boot Record Stage)

- Finding the Bootloader: On older systems, the BIOS reads the first 512-byte sector of the bootable disk (MBR) to find primary boot code. Modern systems use UEFI with GPT partition tables instead.
- Handing Over Control: Control is transferred to the primary boot program to locate the secondary loader.
