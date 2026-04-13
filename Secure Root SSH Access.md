
## Secure Root SSH Access

`Task`: **Your task is to disable direct SSH root login on all app servers within the Datacenter.**

- used $ `ssh user3@server3` to login/connect with server 3.
- used $ `sudo -i` to get inside a interactive shell and run commands as a root.
- used # `sudo passwd root` to create a password for root.
- used # `cat /etc/ssh/sshd_config` to see the content of this file.
- used # `nano /etc/ssh/sshd_config` to edit the file. Updated the field, `PermitRootLogin no`
- used # `systemctl restart sshd` to restart the sshd service to apply the change then used `exit` to come out of the shell and server 

- used below command to login directly as a root but it will not happen as we disabled direct root login. Below is the output:
```
thor@jump-host ~$ `ssh root@server3`
root@server3's password: 
Permission denied, please try again.
root@server3's password:
```

