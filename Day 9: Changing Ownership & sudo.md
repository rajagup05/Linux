## Day 9: Changing Ownership & sudo

**Goal:** Learn to run commands as an administrator.

**Commands:** 

1. **Running Commands as Administrator (`sudo`):**  The `sudo` (superuser do) command allows a permitted user to execute a command as the superuser or another user, as specified by the security policy. This is a safer alternative to logging in as the `root` user directly for all tasks.

**How it Works:** When you prepend `sudo` to a command, the system prompts for a password (either the root password or, in some configurations, your own user password) and, upon successful authentication, executes the command with elevated privileges. Elevated privileges typically persist for a short duration in the current terminal session to avoid repeated password entry.

**Common Uses:**
- Installing system-wide software/packages (e.g., `sudo apt install package-name`).
- Editing system files (e.g., `sudo nano /etc/hosts`).
- Running administrative tools (e.g., `sudo fdisk -l`)
  

2. **Changing File/Directory Ownership (`chown`):** The `chown` (change owner) command changes the user and/or group owner of a given file or directory. You typically need administrator privileges (using `sudo`) to use this command unless you are changing the group to one you are a member of and already own the file. 

**Example:** `sudo chown username filename.txt`


**Lab:** Use `sudo chown root <file>` to change a file's owner to '`root`'. Then, change it back to your username.
