
## Access Control Lists (ACLs)

Access Control Lists (ACLs) in Linux provide a fine-grained permission mechanism that extends beyond the traditional standard UGO (User, Group, Others) permission model. They allow system administrators to grant specific read, write, or execute permissions to individual users or groups without modifying the file's primary ownership or altering existing group memberships.

- `getfacl`: Displays the current ACL entries for a specific file or directory.
- `setfacl`: Modifies, sets, or removes ACL entries on a file or directory.

### Managing Access ACLs:

- Grant user permissions:`setfacl -m u:username:rwx filename`
- Grant group permissions:`setfacl -m g:groupname:rx filename`
- Remove a user's entry:`setfacl -x u:username filename`
- Remove all ACL rules:`setfacl -b filename`
