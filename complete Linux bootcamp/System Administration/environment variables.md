
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
