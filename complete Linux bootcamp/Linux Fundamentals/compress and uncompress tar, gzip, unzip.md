
## compress and uncompress tar, gzip, unzip

### 1. TAR Commands (.tar)

The tar command bundles multiple files and directories into one archive file, preserving file permissions and directory structures. By itself, it does not compress files.

- Compress (Archive): `tar -cvf archive.tar /path/to/directory`. (Flags: `-c` create, `-v` verbose output, `-f` specify archive filename)
- Uncompress (Extract): `tar -xvf archive.tar` (`-x` is for extract)

### 2. GZIP Commands (.gz)

The gzip tool compresses individual files. Note that running gzip on a file will replace the original file with the compressed version.

- Compress: `gzip filename.txt` (Creates `filename.txt.gz` and removes `filename.txt`)
- Uncompress: `gunzip filename.txt.gz` (Restores filename.txt and removes the .gz file)

### 3. Combined TAR and GZIP (.tar.gz or .tgz)

Because gzip cannot compress folders by itself, it is routinely paired with tar. The tar utility provides the -z flag to invoke gzip automatically.

- Compress: `tar -czvf archive.tar.gz /path/to/directory` (`-z` compress using gzip)
- Uncompress: `tar -xzvf archive.tar.gz`





