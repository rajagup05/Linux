
## user account management commands

In Linux, the `useradd`, `groupadd`, `usermod`, `userdel`, and `groupdel` commands form the core suite of tools used by system administrators to manage low-level user accounts and group memberships. Because these commands modify critical system files like `/etc/passwd` and `/etc/group`, they must be executed with sudo or root privileges.

### 1. useradd (Create a New User Account)

The useradd command initializes a brand-new user profile. By default, it adds a new entry to the /etc/passwd file.

Example: Create a user named "bobby" with a home directory and bash shell: `sudo useradd -m -s /bin/bash bobby`

### 2. groupadd (Create a New Group)

The groupadd command establishes a new group identifier (GID) within the system, allowing you to manage shared file permissions for multiple users at once.

Example: Create a new administrative group named "developers": `sudo groupadd developers`
