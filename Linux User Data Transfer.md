
## Linux User Data Transfer 

`Task:` Locate all files (excluding directories) owned by user `mark` within the `/home/usersdata` directory on `App Server 2`. Copy these files while preserving the directory structure to the `/media` directory.

- used $ `ssh user2@server2` to login/connect into the server2.
- used `sudo yum install cpio` to install the `cpio` package
- used  `find /home/usersdata -type f -user mark | cpio -pdm /media` to locate all the files only which belongs to user `mark` in path `/home/userdata`, then used `cpio` command to copy the output of previous command to `/media` folder
=> here user is mark and filetype is regular

- used `cd /media` then `ls -l /media` to check if the required if copied to this location. 

The `cpio` command is highly efficient for large numbers of files and is built to preserve directory paths exactly as they appear in the input. 
- `-p:` Pass-through mode, which copies files from one directory to another.
- `-d:` Automatically creates leading directories where needed.
- `-m:` Preserves file modification times
