
## switch users and sudo access

To switch users and use administrative (sudo) access in Linux, use the su or sudo commands. su switches to another user account using that user's password, while sudo elevates your privileges to run commands as root (or another user) using your own password.

- Run a single command as root: Use sudo followed by the command:`sudo <command>`
- Run a command as a specific user: Use the -u flag:`sudo -u <username> <command>`
- Start an interactive root shell (keep your current environment): Run:`sudo su -`
- Switch to another user completely (requires their password): Run su followed by the target username:`su <username>`
