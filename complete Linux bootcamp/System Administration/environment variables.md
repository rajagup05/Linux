
## environment variables

Environment variables in Linux are system-wide key-value pairs used to share technical configuration data between the operating system, shell sessions, and running applications. Unlike local shell variables, environment variables are globally inherited by child processes and scripts launched from that terminal session.

- List all variables: Run `printenv` or `env` to see every active environment variable.
- View a specific variable: Use `printenv VARIABLE_NAME` or `echo $VARIABLE_NAME`.
- List shell variables: Run `set` without arguments to see both local and environment variables.

- `$PATH`: A colon-separated list of directories the system searches when you run a command.
- `$HOME`: The absolute path to the current user's home directory.
- `$USER`: The username of the currently logged-in user.
- `$PWD`: The absolute path of the present working directory.
- `$SHELL`: The path to the active shell interpreter (e.g., /bin/bash).

### Creating and Modifying Variables

- Local Shell Variable: `MY_VAR="Hello"`
- Environment Variable (Global to the session): `export MY_VAR="Hello"`

- Permanent (User-Wide): To make variables persist across system reboots for your specific user account, add the export command to your shell's configuration file:
  - For Bash: Open `~/.bashrc` using a text editor (like `nano ~/.bashrc`) and append your variable: `export API_KEY="12345"`
- Removing Variables: `unset MY_VAR`

