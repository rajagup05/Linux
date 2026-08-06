
## aliases

In Linux, an alias acts as a custom shortcut or nickname for a command. You use the alias command to map a short word to a longer or more complex command sequence, saving time and avoiding repetitive typing.

### Basic Alias Operations

- Create temporary alias: Type `alias name="command"` in your terminal (e.g., `alias ll="ls -la"`). It works immediately but disappears when you close the session.
- List active aliases: Type `alias` by itself to see all shortcuts currently available in your shell session.
- Remove an alias: Type `unalias name` (e.g., `unalias ll`) to delete the shortcut.

### Making Aliases Permanent

- User profile: Open your shell configuration file (like `~/.bashrc` or `~/.zshrc`) in a text editor.
- Add entry: Insert your alias line at the bottom of the file (e.g., `alias c="clear"`).
- Reload configuration: Run `source ~/.bashrc` to apply the changes to your current terminal session.
- System-wide setup: Add aliases to `/etc/bash.bashrc` using root permissions if you want all users on the machine to access them.

- No dynamic arguments: Standard aliases cannot accept positional parameters (like `alias mycp="cp $1 destination"`). For arguments, write a Bash Functions instead.
- Overriding safety: Use aliases to add safety prompts to destructive commands, such as `alias rm="rm -i"`.
- Bypassing an alias: Prefix your command with a backslash (e.g., `\rm file.txt`) to run the original system command instead of the alias.



### User `.bashrc` File

- Location: Located in the user's home directory at `~/.bashrc` (expanded as `/home/username/.bashrc`).
- Permissions: Owned by the specific user, allowing modification without administrative privileges.
- Scope: Customisations only apply to that specific user's non-login interactive shell sessions.


### Root `.bashrc` File

- Location: Located in the root user's home directory at `/root/.bashrc`.
- Permissions: Owned by root, requiring sudo or root access to modify.
- Scope: Customisations only apply when operating directly as the root user (e.g., after running `sudo -i` or `su`).

### System-Wide Alternative

- Location: Located at `/etc/bash.bashrc` (or `/etc/bashrc` depending on the Linux distribution).
- Scope: Applies globally to all users on the system, including root, unless overridden by individual `.bashrc` files.
