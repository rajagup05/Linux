
## standard output to a file using `tee` command

To route standard output (stdout) to a file while still viewing it in the terminal, use the tee command combined with a pipe (|).

### Basic syntax

This command displays the results on your screen and saves them to the specified file. Warning: If the file already exists, this method will overwrite its content.

`command | tee filename.txt`

eg. `ls -l | tee file_list.txt`

### Append mode (`-a`)

To add the output to the end of an existing file without deleting its current contents, use the `-a` or `--append` flag.

eg. `uptime | tee -a uptime_history.txt`
