
## Important things to remember in Linux

Mastering Linux requires a shift in mindset: everything in Linux is a file, the command line is your friend, and configuration errors are how you learn. Instead of memorizing every command, focus on understanding the core mechanics of the operating system.

### 1. Core Mechanics:

- `Everything is a file`: Devices, directories, and processes are all treated as files. Hardware drives are located in /dev and configurations are plain-text files.
- `Case Sensitivity`: Linux is strictly case-sensitive. Document.txt, document.txt, and DOCUMENT.txt are three completely different files.
- `No \ for paths`: Always use a forward slash (/) to separate directories (e.g., /home/user/files).
- `Hidden files`: Files or folders beginning with a dot (e.g., .bashrc) are hidden. Use ls -a to see them.

### 2. Navigation and File management:

- `pwd`: Prints your current location. Use it if you ever get lost in the file system.
- `ls`: Lists files in a directory. Add -lh to get a human-readable list showing file sizes and permissions.
- `cd`: Moves between folders. Type cd ~ to go straight to your home directory.
- `cp & mv`: Use cp to copy files and mv to move or rename files.
- `rm`: Deletes files. Warning: rm -rf forcefully deletes directories and their contents. Use this with extreme caution.
