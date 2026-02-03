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
=> Give owner full permissions (rwx), group read/execute (rx), and others read-only (r): `chmod u=rwx,g=rx,o=r filename.txt` 


- **Octal Method (Using Numbers):** The octal method uses a three-digit number to represent the permissions for the owner, group, and others, respectively. Each digit is a sum of numeric values assigned to the permissions: 

Permission 	|    Value \
Read (r)	    :    4  \
Write (w)	     :   2  \
Execute (x)	   :   1  \
No permission (-)	: 0

To determine the octal value for a specific set of permissions, you sum the values. For example, read/write/execute (`rwx`) is \(4+2+1=7\). Read/execute (`r-x`) is \(4+0+1=5\)

**Examples:**

=> Set owner rwx (7), group rx (5), others r (4): `chmod 754 filename.txt` \
=> Set all users to have full permissions (rwx): `chmod 777 filename.txt` \
=> Set only the owner to have read/write permissions (600): `chmod 600 filename.txt` 



2. chown: 

**Lab:** Create script.sh. Use chmod u+x to make it executable. Create another file and set its permissions to 740 (rwx r-- ---).
