
## securing linux machine os hardening

Linux OS hardening is the process of securing an operating system by reducing its attack surface, removing unused software, and enforcing strict access controls.

- **Update Software**: Apply all system updates and patches regularly to fix known vulnerabilities.
- **Harden SSH**: Edit `/etc/ssh/sshd_config` to set `PermitRootLogin` no, enforce SSH key authentication instead of passwords, and change the default port.
- **Configure a Firewall**: Use Uncomplicated Firewall (UFW) or `firewalld` to block unneeded ports and deny incoming traffic by default.
- **Manage User Accounts**: Create a non-root administrative user, assign sudo privileges, and lock or disable the direct root account and unused system accounts.
