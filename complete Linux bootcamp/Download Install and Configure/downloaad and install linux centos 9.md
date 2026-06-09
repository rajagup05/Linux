
## Downloaad and Install Linux CentOS 9

To download and install CentOS 9 (CentOS Stream 9), download the official ISO file, flash it to a USB drive using a tool like Rufus, and boot your PC/server from the drive. Follow the graphical installation prompts to set your partitions, create a user, and complete the installation.

### Step1: Download the ISO image

- Visit the official ⁠CentOS Download Page.
- Click on CentOS Stream 9.
- Select your system architecture (typically x86_64 for standard PCs) and download the ISO file.

### Step2: Create a Bootable USB

- Download a USB flashing tool like Rufus (Windows) or BalenaEtcher (Mac/Linux).
- Insert a USB drive (at least 8GB).
- Open the flashing tool, select your CentOS 9 ISO, and flash it to the USB drive.

### Step3: Install CentOS 9

- Restart your computer and press your manufacturer's Boot Menu key (e.g., F12, F11, Esc) to select your USB drive.
- From the initial GRUB menu, select Install CentOS Stream 9.
- Follow the on-screen Anaconda Installer:
  - Localization: Select your language, keyboard layout, and closest Time Zone (e.g., Asia/Kolkata for Patna).
  - Software Selection: Choose Server with GUI if you prefer a graphical desktop, or Minimal Install for a lightweight CLI server.
  - Installation Destination: Select the hard drive where you want to install it and partition it (choose Automatic if you want the installer to handle it).
  - User Settings: Set a strong root password and create a personal user account (check "Make this user administrator").
- Click Begin Installation.
- Once the installation finishes, click Reboot System. Remove the USB drive when the system restarts.









