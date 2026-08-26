
## rollback patches and upgrades

Rolling back patches and upgrades in Linux depends completely on your package manager or filesystem configuration. Red Hat-based systems natively track transaction histories, whereas Debian/Ubuntu-based systems require you to downgrade packages manually or rely on filesystem snapshots.

### 1. RHEL, Fedora, Rocky Linux, & AlmaLinux (DNF / YUM)

- View update history: `sudo dnf history list`
- Undo a specific update: `sudo dnf history undo 15`
- Roll back to a specific point: `sudo dnf history rollback`

### 2. Ubuntu & Debian (APT)

- Find what changed: `less /var/log/apt/history.log`
- Downgrade a specific package: `sudo apt install package_name=version_number`
- Hold the package: `sudo apt-mark hold package_name`
