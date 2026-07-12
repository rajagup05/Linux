
## switch users and sudo access

To switch users and use administrative (sudo) access in Linux, use the su or sudo commands. su switches to another user account using that user's password, while sudo elevates your privileges to run commands as root (or another user) using your own password.

- Run a single command as root: Use sudo followed by the command:`sudo <command>`
- Run a command as a specific user: Use the -u flag:`sudo -u <username> <command>`
- Start an interactive root shell (keep your current environment): Run:`sudo su -`
- Switch to another user completely (requires their password): Run su followed by the target username:`su <username>`


### 1. Execute a Single Administrative Command

Example: `sudo apt update` or `sudo dnf update`.

### 2. Switch Users

Example: `su - john`

### 3. Open an Interactive Root/Admin Shell

`sudo -i` or `sudo su -`

### 4. Grant Sudo Access (Requires Existing Admin Privileges)

On CentOS / RHEL / Fedora: `sudo usermod -aG wheel <username>`
