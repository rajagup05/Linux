
## file and directory permissions

The chmod (change mode) command in Linux and Unix-like operating systems modifies the read, write, and execute permissions of files and directories. It restricts or grants access based on three user classes: the owner (u), the group (g), and all others (o).

### Core Permission Types

Permissions behave slightly differently for files and directories:

    Permission       |        For Files                     |     For Directories
    ------------------------------------------------------------------------
    Read (r)         |   View the file's content.           |     List files inside using ls
    Write (w)        |   Edit or clear the file.            |     Create, delete, or rename files inside.
    Execute (x)      |   Run the file as a script/program.  |     Enter the directory using cd

### Method 1: Numeric (Octal) Mode

Numeric mode uses a three-digit number to assign exact permissions to the Owner, Group, and Others (in that specific order). Each digit is calculated by adding the values of the permissions you want to grant:

- 4 = Read (r)
- 2 = Write (w)
- 1 = Execute (x)
- 0 = No permissions

#### examples: 

- `chmod 755 script.sh`: Owner can do everything (4+2+1=7). Group and Others can only read and execute (4+1=5). Highly common for public scripts and directories.
- `chmod 644 file.txt`: Owner can read and write (4+2=6). Group and Others can only read (4). Standard setting for Web assets and regular text documents.
- `chmod 700 private.txt`: Only the owner has full access (7); everyone else is completely blocked (0).
- `chmod 777 shared/`: Everyone has full access. Warning: Avoid using 777 as it presents a massive security risk.











