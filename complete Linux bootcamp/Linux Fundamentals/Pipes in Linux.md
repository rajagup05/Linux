
## Pipes (`|`) in Linux

In Linux, the pipe command (represented by the vertical bar |) redirects the standard output (stdout) of one command to serve directly as the standard input (stdin) of the next command. This allows you to string multiple small, single-purpose utilities together into a powerful pipeline to manipulate data seamlessly without saving intermediate results to temporary files.

syntax: `command1 | command2`

Data flows strictly from left to right. The terminal will only print the final output produced by the last command in the chain.

### examples: 

#### 1. Search for specific text in a directory listing

Combine ls (list files) with grep (search text) to quickly find a specific file. eg. `ls -l | grep "report"`

#### 2. Count specific active processes

Combine ps (process status), grep (filter text), and wc (word count) to count how many instances of an application are running. eg. `ps aux | grep "nginx" | wc -l`

#### 3. View a long file or output page-by-page

If a command outputs thousands of lines, pipe it into less to read it comfortably. eg. `cat large_log_file.txt | less`

#### 4. Find the largest files in a folder

Combine du (disk usage), sort (organize data), and head (show top results). eg. `du -sh * | sort -hr | head -n 5`

