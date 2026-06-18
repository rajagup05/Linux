
## Filesystem navigation commands

The core commands used to navigate the Linux filesystem are pwd (to find your current location), ls (to list directory contents), and cd (to change directories). Understanding these three utilities allows you to traverse and inspect any directory tree structure in a Linux environment.

### 1. Essential Navigation Commands

- `pwd`: Prints the full absolute path of your current working directory.
- `ls`: Lists files and folders inside the current directory.
  - `ls -l`: Displays a detailed "long" list showing permissions, ownership, size, and modification dates.
  - `ls -a`: Reveals hidden files and folders, which always start with a period.
- `cd`: Changes your active terminal location to a different folder.
  - `cd /path/to/folder`: Moves directly to a specified folder name or absolute path.
  - `cd`: Typing cd with no folder name automatically sends you back to your user home directory.

### 2. Standard Path Shortcuts

- `.` (**Single Dot**): Represents your current active folder.
- `..` (**Double Dot**): Represents the parent folder located directly one level up. Example: cd .. backs out of the current folder.
- `~` (**Tilde**): Represents the logged-in user’s primary home directory. Example: cd ~ returns you straight home.
- `-` (**Dash**): Switches back to the immediate previous folder you were working in. Example: cd - toggles back and forth between two distinct locations.
