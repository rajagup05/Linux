
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

### 3. `cp` (Copy)

The cp command duplicates files or directories from a source to a destination.

- Syntax: `cp [options] source destination`
- Key Flag (`-r` / `-R`): Copies folders recursively, which is required whenever you duplicate a directory containing other files.

examples: 

`cp notes.txt backup.txt` (Duplicates a single file)

`cp -r /my_folder /backup_folder` (Duplicates an entire directory)


### 4. `mv` (Move / Rename)

The mv command serves a dual purpose: moving items to a different path or changing their names. It does not create a duplicate.

- Syntax: `mv [options] source destination`
- Key Flag (`-i`): Interactively prompts you before overwriting an existing file.
- Key Flag (`-f`): Forces the move, overwriting destination files without prompting.

examples:

`mv draft.txt final.txt` (Renames a file in the same directory)

`mv report.pdf Documents/` (Moves a file into another folder)


### 5. `rm` (Remove)

The rm command permanently deletes files or directories. Warning: Linux does not have a native terminal "Trash bin"; operations using rm are irreversible.

- Syntax: `rm [options] item_name`
- Key Flag (`-r`): Deletes a directory and all of its contents recursively.
- Key Flag (`-f`): Forces deletion by ignoring non-existent files and overriding safety prompts.

examples: 

`rm virus.exe` (Deletes a single file)

`rm -rf old_project/` (Permanently wipes out a directory and everything inside it)
