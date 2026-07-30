
## shell scripting

Shell scripting in Linux is the practice of writing a series of commands into a single plain text file to automate repetitive computer tasks. This file is processed by a command-line interpreter known as a shell, with Bash (Bourne-Again Shell) serving as the default choice across most distributions.

### Creating First Script

1. Create the File: Open your terminal and create a new file using a text editor like Nano or Vim. => `nano myscript.sh`
2. Add the Shebang: Write the required "shebang" line at the very top of your file. This points the operating system to the correct interpreter. =>

```
#!/bin/bash
echo "Hello, World!"
```

3. Make it Executable: Save and close the file. By default, new files do not have execution permissions. Grant them using the chmod command => `chmod +x myscript.sh`
4. Run the Script: Execute it from your current directory using `./` => `./myscript.sh`
