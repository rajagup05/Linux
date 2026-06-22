
## Linux File types

Under the core Unix philosophy that "everything is a file," Linux recognizes exactly seven distinct file types.

You can instantly identify a file's type by looking at the very first character of its output string when running the `ls -l` command.

## Overview of the seven file types

1. Regular file (`-`): Stores user data, scripts, images, or binaries. eg. `/etc/passwd`
2. Directory (`d`): Acts as a folder containing lists of other files. eg. `/home/user/`
3. Symbolic link (`l`): Serves as a shortcut pointing to another file path. eg. `/bin/sh`
4. Block device (`b`): Interfaces with hardware that handles data in blocks. eg. `/dev/sda` (Hard drive)
5. Character device (`c`): Interfaces with hardware that stream bytes sequentially. eg. `/dev/null` or `/dev/tty`
6. Named Pipe (`p`): Routes data unidirectionally between local processes. eg. Custom created IPC pipes
7. Local socket (`s`): Enables bidirectional inter-process communication. eg. `/var/run/docker.sock`
