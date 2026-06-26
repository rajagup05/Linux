
## Access Control Lists (ACLs)

Access Control Lists (ACLs) in Linux provide a fine-grained permission mechanism that extends beyond the traditional standard UGO (User, Group, Others) permission model. They allow system administrators to grant specific read, write, or execute permissions to individual users or groups without modifying the file's primary ownership or altering existing group memberships.

- `getfacl`: Displays the current ACL entries for a specific file or directory.
- `setfacl`: Modifies, sets, or removes ACL entries on a file or directory.

### Managing Access ACLs:

- Grant user permissions:`setfacl -m u:username:rwx filename`
- Grant group permissions:`setfacl -m g:groupname:rx filename`
- Remove a user's entry:`setfacl -x u:username filename`
- Remove all ACL rules:`setfacl -b filename`

### Managing default ACLs:

Default ACLs can only be applied to directories. Once set, any new file or subdirectory created inside that directory automatically inherits these permissions.

- Set a default ACL:`setfacl -d -m u:username:rx /path/to/dir`
- Apply recursively to existing files:`setfacl -R -m u:username:rwx /path/to/dir`

### Mask with ACLs:

The mask defines the absolute maximum permissions that any non-owner ACL entry can possess. Even if you explicitly grant a user `rwx` privileges, if the mask is configured to `r--`, that user will only receive read-only effective access.

- Modify the mask:`setfacl -m mask:rw filename`

### How to identify files with ACls:

When you execute an `ls -l` command, files or directories configured with active ACL rules display a plus sign (`+`) right after the traditional permission string (e.g., `-rw-rwxr--+`).
