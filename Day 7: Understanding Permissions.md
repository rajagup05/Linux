## Day 7: Understanding Permissions

**Goal:** Understand the "read, write, execute" (rwx) model.

**Concept:** Analyze the output of `ls -l` (e.g., `-rwxr-xr--`) for User, Group, and Other.

> The "read, write, execute" (rwx) model in Linux is a foundational access control system that defines who can perform which actions on a file or directory.

**User Categories:**
- **User/owner (u):** The person who owns the file or directory (typically the creator).
- **Group (g):** Members of the group associated with the file.
- **Others (o):** All other users who are neither the owner nor a member of the file's group.

**The Permissions: Read, Write, Execute :**

1. **Read (r):**
   - **Octal Value:** 4
   - **Meaning for Files:** View the file's contents.
   - **Meaning for Directories:** List the files within the directory.

2. **Write (w):**
   - **Octal Value:** 2
   - **Meaning for Files:** Modify or delete the file's contents.
   - **Meaning for Directories:** Create, delete, or rename files within the directory.

3. **Execute (x):**
   - **Octal Value:** 1
   - **Meaning for Files:** Run the file as a program or script.
   - **Meaning for Directories:** Enter (traverse/access) the directory or access its metadata.


**Lab:** Create a file and write down its default permissions. Analyze what the User, Group, and Other can do.
