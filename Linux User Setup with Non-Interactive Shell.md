
##  Linux User Setup with Non-Interactive Shell

`Task`: **Create a user named anita with a non-interactive shell on App Server 2.**

- used `ssh user2@server2` to login into the server
- used `sudo useradd anita -s /sbin/nologin` . Here anita is the user being added, -s flag represents a shell, /sbin/nologin implies that command is run in non-interactive shell. 
