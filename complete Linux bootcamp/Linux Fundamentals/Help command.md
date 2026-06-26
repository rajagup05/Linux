
## Help command in Linux

The help command in Linux is a built-in shell utility used exclusively to get documentation for internal shell built-in commands like cd, echo, alias, and pwd. It displays a concise overview of command usage, syntax, and options directly inside your terminal.

Because Linux separates commands into internal (built-in) and external (executable programs), the help command will not work for external tools like ls, grep, or mkdir. For those, you must use alternative tools like the --help flag or man pages.

### help command for built-ins

To use the built-in utility, simply type help followed by the command name.

- List all built-in commands: Type `help` on its own to see every command supported by your current shell.
- Get standard help: Use `help cd` to display syntax and formatting options for the change directory command.
- Get a short description: Run `help -d cd` to output a one-line phrase of what the command does.
- Get the syntax only: Execute `help -s cd` to print a clean template of the command's expected structure.
- Get man-page style output: Run `help -m cd` to organize the built-in information into traditional manual sections.

### Alternative ways to get help in Linux

- The `--help` Flag: Appending --help to almost any external executable (e.g., `ls --help` or `tar --help`) prints a fast, highly scannable breakdown of options without leaving your current terminal line.
- The `man` Command: Running `man <command>` (e.g., `man tar`) opens the complete system reference manual, offering exhaustive documentation, flag definitions, and edge cases
