
## Linux File or Directory Properties

In Linux, every file and directory possesses core properties including file type, access permissions, ownership (user and group), size, links, and modification timestamps. You can view these properties instantly via the terminal using the long listing command ls -l.

### Reading the properties (ls -l) output:\

-rw-r--r--  1  owner_name  group_name  4096  Jun 18 18:00  filename.txt 

**1. File Type (The First Character)**

The very first character of the metadata line identifies what type of resource it is:

- `-`: Regular data file (text, image, binary)
- `d`: Directory (folder)
- `l`: Symbolic link (shortcut pointing to another file)
- `c` or `b`: Device files (character/sequential or block/storage devices)

**2. Access Permissions (The Next 9 Characters)**

The next nine characters are split into three sets of triplets, dictating who can do what:

- **First Triplet (Characters 2–4)**: Permissions for the Owner (the individual user who owns the file).
- **Second Triplet (Characters 5–7)**: Permissions for the Group (users assigned to the file's group).
- **Third Triplet (Characters 8–10)**: Permissions for Others (everyone else on the system).

Each triplet consists of:

- `r` (Read): View file contents, or list files inside a directory.
- `w` (Write): Modify/delete file contents, or add/remove files inside a directory.
- `x` (Execute): Run a file as a program, or enter a directory using the cd command.
- `-`: Permission denied.

**3. Hard link count**

The second column lists how many hard links point to this specific file or directory. For a standard empty directory, this number defaults to 2 because it links to itself (.) and its parent directory (..).

**4. ownership (user and group)**

- **User Owner**: The specific account name that created or controls the file.
- **Group Owner**: The system group that shares access privileges over the file.

**5. Size and Timestamp**

- **Size**: Displayed by default in bytes. Tip: Run ls -lh to view file sizes in human-readable formats like KB or MB.
- **Last Modified**: The date and exact time the file contents were last changed.












