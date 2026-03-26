
### Task is to create a custom user according to the outlined specifications:

1. **Create a user named `john` on `App server 2` server.**

- used `ssh username@server2` to connect to server
- used command `sudo useradd john` to create a user
- changed directory to `/etc/passwd` and used `cat passwd` to view the newly created user details.

  output looks like this: `john:x:1002:1002::/home/john:/bin/bash`

2. **Assign a unique UID `1690` and designate the home directory as `/var/www/john`.**

- used command `sudo usermod -u 1690 john` to change uid
- used command `sudo usermod john -d /var/www/john` to move user's home directory
- To check this again changed directory to `/etc/passwd` and used `cat passwd` to view the updated user details.

  output looks like this: `john:x:1690:1002::/var/www/john:/bin/bash`


**john:x:1690:1002::/home/john:/bin/bash** :

- `john` **(Username):** The login name of the user.
- `x` **(Password Placeholder)**: Indicates that the actual encrypted password is not stored in this file, but rather in the secure `/etc/shadow` file.
- `1690` **(User ID - UID)**: The unique numerical ID assigned to the user "john".
1002 (Group ID - GID): The numerical ID of the user's primary group.
- `` **(Comment/GECOS)**: This field is empty (between the two colons). It is usually used for user information, such as full name or phone number.
- `/home/john` **(Home Directory)**: The path to the user's personal home directory.
- `/bin/bash` **(Shell)**: The default command interpreter (shell) that runs when the user logs in
