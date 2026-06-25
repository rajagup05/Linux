
## file ownership commands chown and chgrp

In Linux and Unix-like operating systems, chown (change owner) and chgrp (change group) are the core administrative commands used to manage file and directory ownership. While chown is highly versatile and can alter both users and groups, chgrp is dedicated exclusively to modifying group assignments.

- `chown`: Changes user ownership, group ownership, or both simultaneously.
- `chgrp`: Changes only the group ownership.
- `Privileges`: Only the root superuser can use chown to hand over ownership to another user. Normal users can use chgrp (or chown :group) only if they own the file and belong to the target group.

### The chown Command

The chown command modifies the user and/or group that owns a specific file or directory.

syntax: `sudo chown [OPTIONS] [USER][:GROUP] filename`

#### examples:

- Change the owner only: `sudo chown alice report.txt`
- Change both the owner and the group: `sudo chown alice:developers report.txt`
- Change the group only (using chown): `sudo chown :developers report.txt`
- Change ownership recursively (applies to a directory and all files inside it): `sudo chown -R alice:developers /var/www/html`
