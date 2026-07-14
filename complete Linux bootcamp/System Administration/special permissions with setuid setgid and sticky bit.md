
## special permissions with setuid setgid and sticky bit 

SUID (Set User ID), SGID (Set Group ID), and the Sticky Bit are advanced Linux file permissions that extend standard read, write, and execute (rwx) capabilities to handle specialized security and collaboration tasks.

### 1. SUID (Set User ID)

- When an executable file has SUID set, any user running it temporarily inherits the privileges of the file owner rather than the person executing it.
- The `/usr/bin/passwd` command. Regular users must modify the protected `/etc/shadow` file to change their passwords. Because passwd is owned by root and has SUID set, it runs with temporary root privileges.
- How to Set: `chmod u+s filename` (Symbolic) OR `chmod 4755 filename` (Octal)


### 2. SGID (Set Group ID)

- SGID behaves differently depending on whether it is applied to a file or a directory.
- On a File: The program runs with the privileges of the file's group rather than the caller's group.
- Symbolic Representation: Replaces the group's execute x with a lowercase s (or a capital S if group execution is missing).
- How to Set: `chmod g+s path_name` (Symbolic) OR `chmod 2755 path_name` (Octal)
