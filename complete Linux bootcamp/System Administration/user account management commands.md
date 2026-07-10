
## user account management commands

In Linux, the `useradd`, `groupadd`, `usermod`, `userdel`, and `groupdel` commands form the core suite of tools used by system administrators to manage low-level user accounts and group memberships. Because these commands modify critical system files like `/etc/passwd` and `/etc/group`, they must be executed with sudo or root privileges.

### 1. useradd (Create a New User Account)

The useradd command initializes a brand-new user profile. By default, it adds a new entry to the /etc/passwd file.

Example: Create a user named "bobby" with a home directory and bash shell: `sudo useradd -m -s /bin/bash bobby`

### 2. groupadd (Create a New Group)

The groupadd command establishes a new group identifier (GID) within the system, allowing you to manage shared file permissions for multiple users at once.

Example: Create a new administrative group named "developers": `sudo groupadd developers`

### 3. usermod (Modify an Existing User)

The usermod command modifies an existing user's attributes, such as their username, home directory location, or group attachments.

Example: Append the user "bobby" to the "developers" group: `sudo usermod -aG developers bobby`

### 4. userdel (Delete a User Account)

The userdel command completely removes a user account from the system registry.

Example: Cleanly erase user "bobby" and all of their personal files: `sudo userdel -r bobby`

### 5. groupdel (Delete a Group)

The groupdel command deletes an obsolete or unneeded group from the /etc/group file.

Example: Delete the "developers" group: `sudo groupdel developers`
