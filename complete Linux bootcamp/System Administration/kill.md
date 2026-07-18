
## kill command in linux

The kill command in Linux is a built-in utility used to send termination or operational signals to running processes using their unique Process ID (PID). By default, running kill <PID> sends a SIGTERM (Signal 15), which politely requests a program to close while allowing it to save its progress and release resources.

syntax: `kill [OPTIONS] [SIGNAL] PID`

### Step 1: Find the Process ID (PID)

- `pgrep firefox`: Displays the PID of a specific application by its name.
- `ps aux | grep firefox`: Generates a detailed list of all system tasks to help you manually inspect PIDs.

### Step 2: Choose the Correct Signal

- You can change the intensity of the command by specifying custom termination flags. Use `kill -l` to view all available system flags.
