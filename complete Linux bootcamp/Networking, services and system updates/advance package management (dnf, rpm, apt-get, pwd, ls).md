
## advance package management (dnf, rpm, apt-get, pwd, ls)

To master advanced Linux system administration, you need to understand both high-level package managers (dnf, apt-get) that resolve dependencies automatically, and low-level primitives (rpm) that manage raw packages. Combining these with filesystem operations (pwd, ls) allows you to audit packages, track configuration files, and troubleshoot local repositories efficiently.

### 📦 1. Advanced DNF / YUM (Red Hat Ecosystem)

dnf manages package transactions, dependencies, and local repositories.

- Transaction History: View, roll back, or undo previous package changes.

```
dnf history          # List recent package installations/updates
dnf history undo 12  # Revert the exact changes made in transaction #12
```

- System Auditing: Find orphaned packages or files that do not belong to any package.

```
dnf list extras      # Show packages not found in current repositories
dnf repoquery --file /etc/httpd/conf/httpd.conf  # Find which package owns a specific file
```

- Module Management: Switch between software stream versions (e.g., Node.js 18 vs Node.js 20) on the fly.

```
dnf module list nodejs       # Check available streams
dnf module enable nodejs:20  # Switch to stream 20
```

### 🛠️ 2. Advanced RPM (Low-Level Red Hat Tool)

rpm interacts directly with individual .rpm files and the local database without checking remote networks.

- Package Verification: Check if critical system files have been modified, deleted, or corrupted since installation.

```
rpm -Va  # Verify all installed packages (outputs changes to sizes, MD5, permissions)
```

- Querying Uninstalled Files: Inspect a downloaded .rpm package before installing it onto the system.

```
rpm -qpl package.rpm  # List all files contained inside an uninstalled package
rpm -qpi package.rpm  # Show metadata, author, and description of the file
```

- Database Maintenance: Fix a corrupted RPM database if package installations freeze.

```
sudo rm -f /var/lib/rpm/__db*  # Remove stale lock files
sudo rpm --rebuilddb           # Rebuild the package index database
```

### 🌍 3. Advanced APT-GET (Debian/Ubuntu Ecosystem)

apt-get and apt manage .deb packages via automated dependency resolution.

- Fixing Broken Dependencies: Force the system to resolve missing or broken dependencies automatically.

```
sudo apt-get install -f  # "Fix broken" flag repair script
```

- Intelligent Upgrades: Upgrade the entire system, handling changing dependencies and removing obsolete packages safely.

```
sudo apt-get dist-upgrade  # Aggressively handles architecture changes and dependencies
```

- System Cleanup: Purge configuration files alongside the binary applications to keep the system clean.

```
sudo apt-get purge nginx      # Deletes the application AND its config files
sudo apt-get autoremove --purge  # Cleans up orphaned dependencies and their configs
```

