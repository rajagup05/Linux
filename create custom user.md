
### Task is to create a custom user according to the outlined specifications:

1. **Create a user named `john` on `App server 2` server.**

- checked current host name using command `hostname`.
- used `sudo hostname [HOSTNAME]` command to change to the desired Host.
- used command `sudo useradd john` to create a user
- changed directory to `/etc/passwd` and used `cat passwd` to view the newly created user details.

  output looks like this: `john:x:1002:1002::/home/john:/bin/bash`

2. **Assign a unique UID `1690` and designate the home directory as `/var/www/john`.**

- used command `sudo usermod -u 1690 john` to change uid
- used command `sudo usermod john -d /var/www/john` to move user's home directory
- To check this again changed directory to `/etc/passwd` and used `cat passwd` to view the updated user details.
