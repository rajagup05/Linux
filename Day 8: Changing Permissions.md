## Day 8: Changing Permissions

**Goal:** Learn to change file permissions.

**Commands:** 

1. **chmod (Change Mode):** The chmod command modifies the access permissions of files and directories for a certain user, group or others.

It supports two primary methods: symbolic and octal.

- **Symbolic Method (Using Letters and Symbols):** The symbolic method uses letters to define the changes. The syntax follows this structure: `chmod [who][operator][permissions] filename`.
  - **Who (The affected users):** options => u `(user/owner)`, g `(group)`, o `(others)`, a `(all)`
  - **Operator (What to do):** options => + `(add permission)`, - `(remove permission)`, = `(set exact permissions)`
  - **Permissions (The permissions):** options => r `(read)`, w `(write)`, x `(execute)`
 
**eg.**

=> Add execute permission for the owner: `chmod u+x filename.txt` \
=> Remove write permission for the group and others: `chmod go-w filename.txt` \
=> Set read-only permissions for everyone: `chmod a=r filename.txt` \
=> Give owner full permissions (rwx), group read/execute (rx), and others read-only (r): `chmod u=rwx,g=rx,o=r filename.txt` \


- Octal Method (Using Numbers):


2. chown: 

**Lab:** Create script.sh. Use chmod u+x to make it executable. Create another file and set its permissions to 740 (rwx r-- ---).
