
## securing linux machine os hardening

Linux OS hardening is the process of securing an operating system by reducing its attack surface, removing unused software, and enforcing strict access controls.

- **Update Software**: Apply all system updates and patches regularly to fix known vulnerabilities.
- **Harden SSH**: Edit `/etc/ssh/sshd_config` to set `PermitRootLogin` no, enforce SSH key authentication instead of passwords, and change the default port.
- **Configure a Firewall**: Use Uncomplicated Firewall (UFW) or `firewalld` to block unneeded ports and deny incoming traffic by default.
- **Manage User Accounts**: Create a non-root administrative user, assign sudo privileges, and lock or disable the direct root account and unused system accounts.

- **Remove Unused Services**: Disable or remove unneeded packages, background services, and legacy protocols to minimize exposure.
- Enable Auditing and Logging: Set up tools like auditd, fail2ban, and Lynis to monitor unauthorized access attempts and run security audits.
- **Remove Unwanted Packages & Dependencies**: Minimizing installed software reduces your attack surface. Unused programs or legacy dependencies can contain vulnerabilities that could be exploited.
- **Check & Manage Listening Ports**: Every open port is a potential entry point. You should periodically verify what services are listening for network connections.
- **Configure SELinux (Security-Enhanced Linux)**: SELinux adds Mandatory Access Control (MAC) to the system kernel. It ensures that even if an attacker compromises a service (like Apache), they cannot access unauthorized parts of the file system.
