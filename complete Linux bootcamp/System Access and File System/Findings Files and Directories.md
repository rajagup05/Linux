
## Finding Files and Directories

The primary and most powerful tool for finding files and directories in Linux is the find command, which searches your filesystem in real-time based on a variety of criteria. For instant searches using a pre-built database, you can use the locate command.

## Find

The basic syntax is: `find [path] [options] [expression]`. If you omit the path, it defaults to your current working directory.

### Find by name:

- **Exact Match**: `find . -name "filename.txt"` (Searches the current directory and subdirectories).
- **Case-Insensitive**: `find /home -iname "project"` (Matches "Project", "PROJECT", etc.).
- **Using Wildcards**: `find /var/log -name "*.log"` (Finds all files ending in .log).

### Find by type

- **Files only**: `find /etc -type f -name "nginx.conf"`
- **Directories only**: `find /var -type d -name "www"`
