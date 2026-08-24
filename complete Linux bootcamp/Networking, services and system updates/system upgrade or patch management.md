
## system upgrade or patch management

Linux patch management and system upgrades are the core processes used to secure, stabilize, and update the Linux operating system kernel and its installed packages. Patching specifically refers to targeted updates that resolve vulnerabilities or bugs, while upgrades involve moving packages or the entire OS to a newer major or minor release.

### Command-Line Patching by Distribution

#### Debian / Ubuntu Systems (APT)

- Update package index: `sudo apt update`
- Install available upgrades: `sudo apt upgrade`
- Perform full distribution upgrade: `sudo apt dist-upgrade`
- Install security-only patches: `sudo apt install unattended-upgrades` (requires configuration)
