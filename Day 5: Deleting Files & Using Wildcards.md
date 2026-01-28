## Day 5: Deleting Files & Using Wildcards

**Goal:** Learn to delete items and use the * wildcard.

## Commands:  

In Linux, these commands are used to delete files and folders. We should be careful, as terminal deletions are permanent and do not go to a "Trash" bin. 

> **rm(Remove):** The standard command for deleting files. For eg. `rm filename.txt`
- **For Multiple Files:** `rm file1.txt file2.txt`.

> **rmdir(Remove Directory):** A "safe" command used exclusively for deleting empty directories. eg. `rmdir foldername`

>[!NOTE]
>If the folder contains even one file, rmdir will fail with an error. This prevents accidental loss of data.

- **To Remove Parents:** `rmdir -p a/b/c` removes all three directories if they are all empty.

> **rm -r (Recursive Remove):** Used to delete a directory and everything inside it (files and subdirectories).  eg. `rm -r foldername`

> [!Warning]
> Combining this with `-f (rm -rf)` forces the deletion without asking for any confirmation, even for write-protected files. 


> * (Wildcard/Glob): The asterisk acts as a "wildcard" representing everything in a specific context.

eg. 
- `rm *`: Deletes all files in your current directory (but ignores subdirectories).
- `rm -r *`: Deletes everything in the current directory, including all folders and their contents.
- `rm *.txt`: Deletes only files ending in .txt. 



**Lab:** Use `rm *.txt` to delete all text files from a folder, then use rmdir to delete the empty folder.
