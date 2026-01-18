## Day 1: Basic Navigation

**Goal**: Learn to move around the filesystem.

### Commands: 

> **pwd (Print Working Directory)** => Shows the full path of your current location in the file system (e.g., /home/user/Documents)

> **ls (List)** =>
- Lists the files and subdirectories within the current directory.
- **ls -a** lists all files, including hidden ones (starting with a dot). 

> **cd (Change Directory)** =>
- **cd /** => Moves you to the root directory (the top of the file system).
- cd ~ => Also moves you to your home directory
- **cd ..** => Moves you up one directory level (to the parent directory).
- **cd <directory_name>** : Moves into a specific subdirectory (e.g., cd Downloads).

> **cd -** => this command in Linux (and other Unix-like shells) is a shortcut to change the current working directory to the previous one you were in.
- The shell stores the path to the previous working directory in a special environment variable called $OLDPWD. When you use cd -, the command essentially navigates to the directory stored in $OLDPWD and updates the variable for the next use. 

**Lab**: Navigate to /var/log, list contents, and return home.
