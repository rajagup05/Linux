
## Data Backup for Developer

`Task:` The jump host server hosts a directory named `/data`, serving as a repository for various developers non-confidential data. Developer `ammar` has requested copy of their data stored in `/data/ammar`. The System Admin team has provided the following steps to fulfill this request:

a. Create a compressed archive named `ammar.tar.gz` of the `/data/ammar` directory.
b. Transfer the archive to the `/home` directory on the Jump Host Server.

solution: 

- used
```
$ `cd /data/ammar/` 
thor@jump-host /data/ammar$ `ls` => and got below output:
```
```
nautilus1.txt  nautilus2.txt  nautilus3.txt
```
