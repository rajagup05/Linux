
## Secure Root SSH Access

`Task`: **Your task is to disable direct SSH root login on all app servers within the Datacenter.**

- used $ `ssh user3@server3` to login/connect with server 3.
- used $ `sudo -i` to get inside a interactive shell and run commands as a root.
- used # `sudo passwd root` to create a password for root.
- used # `cat /etc/ssh/sshd_config` to see the content of this file.
- used # `nano /etc/ssh/sshd_config` to edit the file. Updated the field, `PermitRootLogin no`
- used # `systemctl restart sshd` to restart the sshd service to apply the change then used `exit` to come out of the shell and server 
- 
