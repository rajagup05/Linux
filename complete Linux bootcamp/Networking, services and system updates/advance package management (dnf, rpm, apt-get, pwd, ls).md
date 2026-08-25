
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

