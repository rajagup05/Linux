
## Data Backup for Developer

`Task:` **The jump host server hosts a directory named `/data`, serving as a repository for various developers non-confidential data. Developer `ammar` has requested copy of their data stored in `/data/ammar`. The System Admin team has provided the following steps to fulfill this request:**

**a. Create a compressed archive named `ammar.tar.gz` of the `/data/ammar` directory.** \
**b. Transfer the archive to the `/home` directory on the Jump Host Server.**

solution: 

- used
```
$ `cd /data/ammar/` 
thor@jump-host /data/ammar$ `ls`
```
and got below output:

```
nautilus1.txt  nautilus2.txt  nautilus3.txt
```
- used $ `tar -cvzf ammar.tar.gz /data/ammar/` and got below output, Here `c` tells we are creating a file, `v` is for verbose output, `f` represents a file, `z` is used because we are creating gunzip file:
```
tar: Removing leading `/' from member names
/data/ammar/
/data/ammar/nautilus2.txt
/data/ammar/nautilus3.txt
/data/ammar/nautilus1.txt
```
