
## Terminal commands clear exit script

To handle screen clearing and script termination in Linux, use the clear command to clean your terminal view and the exit command to close sessions or end shell scripts.

### The `clear` Command

The clear command wipes the visible terminal screen, moving previous outputs up into the scrollback buffer.

- `clear` - Clears the current screen.
- `clear -x` - Clears the screen but keeps your current cursor position.
- Shortcut: Press `Ctrl + L` to clear the screen instantly without typing a command.
- Alternative: Use the `reset` command if your terminal gets corrupted or displays broken text.

### The `exit` Command

- The exit command terminates the current shell process, closing the terminal tab or ending a running script.
- `exit` - Closes the current terminal session or stops a script cleanly.
- Shortcut: Press `Ctrl + D` on an empty line to log out or close the shell.

### `script` utility in Linux

The script utility in Linux records all inputs and outputs of your terminal session and saves them directly into a typescript log file.

To start recording, simply type the command into your terminal: `script`

- Default Save: By default, it saves everything into a file named `typescript` in your current directory.
- Stop Recording: Type `exit` or press `Ctrl + D` to save the file and stop logging.
