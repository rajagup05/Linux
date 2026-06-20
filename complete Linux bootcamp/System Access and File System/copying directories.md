
## copying directories

To copy a directory in Linux, use the cp command with the -r (recursive) flag: cp -r source_directory destination_directory. Without the -r flag, the terminal will throw an error and refuse to copy the folder.

- `cp -r /path/to/source_dir /path/to/destination_dir` : Duplicates a folder and its contents
- `cp -a /path/to/source_dir /path/to/destination_dir` : Preserves all file attributes, permissions, timestamps, and symbolic links. This is the safest option for backups
