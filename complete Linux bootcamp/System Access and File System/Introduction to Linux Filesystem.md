
## Introduction to Linux Filesystem

The Linux file system is a hierarchical tree structure that organizes all data, devices, and programs. Unlike Windows, it does not use drive letters. Everything originates from a single top-level root directory denoted by a forward slash (/).

A directory tree branches outward from the root, dictating where specific files and configurations live. Key subdirectories include:

- `/bin` & `/sbin`: Essential user commands (like ls or cp) and system binaries used for administration.
- `/boot`: Files, kernels, and the bootloader required to successfully start up the operating system.
- `/dev`: Device files, representing hardware components (like hard drives or terminals), as Linux treats everything like a file.
- `/etc`: Core system-wide configuration files and startup scripts that dictate system behavior.
- `/home`: Personal directories for standard users. Each user gets their own folder (e.g., /home/username) to store files and settings.
- `/lib`: Shared libraries required by system programs to run.
- `/proc` & `/sys`: Virtual, pseudo-file systems that provide real-time information about the kernel and running processes.
- `/tmp`: Temporary files that are usually deleted upon reboot.
- `/usr`: A secondary hierarchy for user applications, libraries, and read-only programs.
- `/var`: Variable data files like system logs, emails, and database files that change frequently.
