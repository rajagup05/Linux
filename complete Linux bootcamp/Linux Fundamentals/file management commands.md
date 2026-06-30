
## file management commands 

Linux file management commands control the creation, movement, duplication, and destruction of files and directories directly through the terminal.

### 1. `mkdir` (Make Directory)

The mkdir command creates one or more new, empty folders.

- Syntax: `mkdir [options] directory_name`
- Key Flag (`-p`): Creates nested parent directories automatically without throwing an error if they do not exist yet.

examples: 

`mkdir projects` (Creates a single folder)

`mkdir -p photos/2026/summer` (Creates the entire folder structure at once) 

### 2. `rmdir` (Remove Directory)

The rmdir command deletes only completely empty directories as a protective safeguard.

- Syntax: `rmdir [options] directory_name`
- Key Flag (`-p`): Removes the specified directory and its parent directories if they become empty after the deletion.

Example: `rmdir projects`
