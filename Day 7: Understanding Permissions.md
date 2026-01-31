## Day 7: Understanding Permissions

**Goal:** Understand the "read, write, execute" (rwx) model.

**Concept:** Analyze the output of `ls -l` (e.g., `-rwxr-xr--`) for User, Group, and Other.

> The "read, write, execute" (rwx) model in Linux is a foundational access control system that defines who can perform which actions on a file or directory.

**Categories:**
- **User/owner (u):** The person who owns the file or directory (typically the creator).
- **Group (g):** Members of the group associated with the file.
- **Others (o):** All other users who are neither the owner nor a member of the file's group. 

**Lab:** Create a file and write down its default permissions. Analyze what the User, Group, and Other can do.
