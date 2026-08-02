
## input and output of a script

In Linux, a script interacts with its environment using Standard Data Streams, which are identified by numeric file descriptors. Every script you run automatically opens three default streams: Standard Input (stdin) for receiving data, Standard Output (stdout) for displaying successful results, and Standard Error (stderr) for reporting problems.

### 1. Input in a Script

A Linux script can accept input through interactive prompts, command-line arguments, or redirected files.

- Interactive Input (read): The read command pauses execution and waits for the user to type something via stdin.
```
#!/bin/bash
echo "Enter your name:"
read user_name
echo "Hello, $user_name!"
```
- 
