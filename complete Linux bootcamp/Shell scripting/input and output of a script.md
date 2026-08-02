
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
- Command-Line Arguments: You can pass data directly into a script when you invoke it using positional variables. `$1`, `$2`, `$3`... represent the first, second, and third arguments. `$@` represents all arguments combined.
```
#!/bin/bash
# Run this as: ./script.sh Alice Bob
echo "First user is: $1"  # Outputs: Alice
echo "Second user is: $2" # Outputs: Bob
```
- Input Redirection (<): You can force a script or a command inside it to read its stdin from a file instead of the keyboard:
```
# Feeds the text inside names.txt directly into the script
./script.sh < names.txt
```

### 2. Output in a Script

