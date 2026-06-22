
## Soft links and Hard links

In Linux, a hard link is an additional filename pointing directly to the same underlying data structure on disk (inode), while a soft link (or symbolic link/symlink) is a shortcut file that contains the text path of another file.

      Feature                       |       Hard Link                                     |     Sodt link (symlink)
      
      Target Reference                  Points to the file's inode.                          Points to the file's path/name.
      Inode Number                      Same as the original file.                           Unique, independent inode number.
      Cross File System                 Cannot span across different filesystems.            Can cross different filesystems.
      Directory Linking                 Not allowed for directories.                         Allowed for both files and directories.
      If Original is Deleted            Data remains accessible through the hard link.       Link breaks and becomes a "dangling link".
      Storage Size                      Same size as the original data.                      Tiny size (only stores the path string).


### How to create them:

#### creating a Hard link: 

`ln source_file.txt hard_link.txt`

#### creating a soft link: 

`ln -s /absolute/path/source_file.txt soft_link.txt`

