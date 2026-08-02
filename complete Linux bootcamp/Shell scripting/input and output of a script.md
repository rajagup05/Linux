
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

Scripts output information using commands like echo or printf. By default, both success messages and errors print to your terminal window.

- Normal Output (stdout):
```
echo "This is a normal success message." 
```
- Error Output (stderr): To explicitly throw an error, you must redirect your output to file descriptor 2 (>&2)
```
echo "Error: Something went wrong!" >&2
```

### 3. Output Redirection and Pipes

Once a script generates output, the Linux shell allows you to redirect or channel that data elsewhere.

- Overwrite File (>): Sends stdout to a file, overwriting its existing contents.
```
./script.sh > output.txt
```
- Append to File (>>): Appends stdout to the end of an existing file.
```
./script.sh >> log.txt
```
- Redirect Errors Only (2>): Captures only the stderr messages into a file.
```
./script.sh 2> error_logs.txt
```
- Silence All Outputs (>/dev/null 2>&1): Completely discards both normal output and error logs by sending them to a virtual "black hole".
```
./script.sh > /dev/null 2>&1
```
- The Pipe Operator (|): Passes the stdout of your script directly as the stdin for another command.
```
./script.sh | grep "Critical"
```
