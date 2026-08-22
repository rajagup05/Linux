
## rsync 

`rsync` (Remote Synchronization) is a highly efficient command-line utility in Linux used for copying and synchronizing files and directories either locally or across remote servers. Unlike standard cp or scp commands, rsync uses a unique delta-transfer algorithm that only transmits the differences (changes) between the source and destination files, significantly reducing data usage and transfer times.

### syntax

`rsync [OPTIONS] SOURCE DESTINATION`

- Local to Local: `rsync -av /src/dir/ /dest/dir/`
- Local to Remote (Push): `rsync -av /src/dir/ user@remote_host:/dest/dir/`
- Remote to Local (Pull): `rsync -av user@remote_host:/src/dir/ /dest/dir/`
