
## Service User Creation without Home Directory

`Task`: **Create a user named jim in App Server 3 without a home directory.**

- used `ssh user3@server3`  to connect/login into this server.
- used `sudo useradd jim -M` to create a user `jim` without a home directory 

> Here, `-M` (or `--no-create-home`) option: This Flag creates the user account but skips the creation of the `/home/jim directory`

