
## standard output to a file using `tee` command

To route standard output (stdout) to a file while still viewing it in the terminal, use the tee command combined with a pipe (|).

### Basic syntax

This command displays the results on your screen and saves them to the specified file. Warning: If the file already exists, this method will overwrite its content.

`command | tee filename.txt`

eg. `ls -l | tee file_list.txt`

### Append mode (`-a`)

To add the output to the end of an existing file without deleting its current contents, use the `-a` or `--append` flag.

eg. `uptime | tee -a uptime_history.txt`

### Capture Errors and Output Together (`2>&1`)

By default, tee only catches standard output (stdout) and ignores standard error (stderr). To save both normal output and error logs to your file, redirect stderr into stdout first:

eg. `command 2>&1 | tee filename.txt`

### Write to Multiple Files

You can split the data stream into multiple files at the exact same time by listing them after the command.

eg. `command | tee log1.txt log2.txt log3.txt`

### Writing to Privileged Files (sudo tee)

Standard file redirection operators like > will fail if you try to route output to a protected system file, even if you start the command with sudo. Use sudo tee instead to bypass this issue:

eg. `echo "127.0.0.1 test.local" | sudo tee -a /etc/hosts`


