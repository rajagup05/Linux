
## Linux vs Windows commands

Linux and Windows use different underlying syntax architectures for their command-line interfaces. Linux terminal environments (like Bash) derive from UNIX roots, passing raw text strings between simple, single-purpose utilities. Windows Command Prompt (CMD) stems from MS-DOS heritage, while its modern counterpart, PowerShell, transfers complex structured object data rather than flat text.

**command description**      |             **in Linux**                 |     **in Windows**

- Lists files and directories with detail:     `ls -l`        |       `dir`
- Prints the active directory path:         `pwd`        |     `cd (or chdir)`
- Changes the current working directory:       `cd [path]`      |        `cd [path]`
- Generates a new directory folder:       `mkdir [name]`      |       `mkdir [name] (or md)`
- Deletes an empty directory folder:       `rmdir [name]`      |     `rmdir [name]`
- Removes files from the storage drive:       `rm [file]`      |       `del [file]`
- Duplicates an existing file:       `cp [src] [dest]`    |      `copy [src] [dest]`
- Moves or renames files and folders:       `mv [old] [new]`      |      `move / ren`
- Prints the raw text contents of a file:       `cat [file]`    |      `type [file]`
- Finds specific text string matches:       `grep "[text]"`    |       `find "[text]"`
- Purges all visible text from the screen:     `clear`   |     `clr`
- Displays running application tasks:     `ps aux`    |    `tasklist`
- Forces a running task to terminate:     `kill [PID]`    |    `taskkill /pid [PID]`
