
## Day 4: Copying & Moving Files

**Goal: Learn to copy, move, and rename items.**

**Commands:** 

> **cp (copy):** The cp command is used to duplicate files or directories from one location to another, leaving the original intact.

eg.
- `cp file1.txt file2.txt` : Duplicates `file1.txt` and names the copy `file2.txt` in the current directory.
- `cp file.txt /home/user/Documents/` : Copies `file.txt` into the `/home/user/Documents/` directory with the same name.
- `cp file1.txt file2.txt backup/` : Copies `file1.txt` and `file2.txt` into the `backup/` directory.
- `cp -r my_folder /home/user/backup/` : The -r (recursive) option is mandatory for copying entire directories and their contents.


> **mv (move):** The mv command is used to move files or directories from one location to another, which removes the original from its source location. It is also the command used for renaming files and directories.

eg.
- `mv file.txt /home/user/Documents/` : Moves `file.txt` from the current directory to `/home/user/Documents/`
- `mv oldname.txt newname.txt` : Renames `oldname.txt` to `newname.txt` in the same location. The file still has its original timestamp.
- `mv file1.txt new_location/file2.txt` : Moves `file1.txt` to the `new_location/` directory and renames it to `file2.txt`
- `mv my_folder backup/` : Moves `my_folder` and its entire contents to the `backup/` directory.

**Lab:** Copy `note1.txt` to `note1_copy.txt`. Rename `note2.txt` to `important.txt`. Move all `.txt` files into a new Notes sub-directory. 
