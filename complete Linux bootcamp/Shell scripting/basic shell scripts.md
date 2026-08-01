
## basic shell scripts

Shell scripting allows you to automate repetitive tasks in Linux and Unix-like operating systems by saving a sequence of commands into a plain text file. The GeeksforGeeks Linux Shell Scripting Guide indicates that Bash (Bourne Again Shell) is the standard default interpreter used for writing these scripts.

### How to Create and Run Your First Script

- Create a text file with a `.sh` extension (e.g., `myscript.sh`).
- Add a shebang line `#!/bin/bash` as the absolute first line to tell the operating system which interpreter to use.
- Write your commands directly beneath the shebang line.
- Grant execution permissions to the script file by running `chmod +x myscript.sh` in your terminal.
- Run the script by typing `./myscript.sh` into your terminal window.

### example code templates

#### 1. Hello World (Basic Input/Output)

```
#!/bin/bash
# Prompt the user for input
echo "What is your name?"
read user_name

# Display a customized greeting
echo "Hello, $user_name! Welcome to shell scripting."
```

#### 2. Conditional Logic (If/Else)

```
#!/bin/bash
echo "Enter a number:"
read num

# Check if the number is greater than 10
if [ $num -gt 10 ]; then
    echo "The number is greater than 10."
else
    echo "The number is 10 or less."
fi
```

#### 3. Iteration (Loops)

```
#!/bin/bash
# Loop through a set range of numbers
for i in {1..5}
do
   echo "Current loop iteration: $i"
done
```
