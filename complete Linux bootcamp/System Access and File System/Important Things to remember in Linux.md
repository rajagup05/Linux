
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

### 3. Safety & Permissions:

- `Don't Run as Root`: Avoid logging in or running the terminal as the root (administrator) user. Use sudo only when elevated privileges are needed.
- `Beware the Almighty Command`: The command `rm -rf /` will recursively wipe your entire hard drive without asking for confirmation. Double-check paths before hitting Enter.
- `Understand chmod & chown`: File security relies on user permissions (Read, Write, Execute). Always verify who owns a file using `ls -l`

### Built-in Help:

- `man command`: Use `man [command_name]` (e.g., `man grep`) to read the official manual page for any tool.
- `--help flag`: Most commands offer a quick summary of their options by typing [command_name] --help.
- `tldr tool`: If man pages feel too dense, use tldr or the web version of TLDR Pages for quick, practical, use-case examples.

### Text processing and Pipes:

- `Piping (`|`)`: The pipe symbol sends the output of one command directly into the input of another. For example: `ls -l | grep "test"` lists all files and then filters only the ones containing "test".
- `Redirection`: Use `>` to overwrite a file with command output, and `>>` to append to the bottom of it (e.g., `echo "hello" > file.txt`).









