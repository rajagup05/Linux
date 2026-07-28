
## tmux command in linux

### Managing Sessions (From the standard terminal)

- `tmux` - Starts a new unnamed session.
- `tmux new -s <name>` - Creates a new session with a specific name.
- `tmux ls` - Lists all active running sessions.
- `tmux attach -t <name>` - Reconnects to a detached session.
- `tmux kill-session -t <name>` - Terminates a specific session completely.

### In-Session Keyboard Shortcuts

Once inside a tmux session, you control everything using the Prefix key combination: Ctrl + b. Press Ctrl + b, release them, and then immediately press one of the keys listed below.

- `d`: Detach from the current session (leaves it running safely in the background).
- `s`: Open an interactive list to switch between sessions.

- `c`: Create a new window.
- `n`: Move to the next window.
- `p`: Move to the previous window.
- `,`: Rename the current window.
- `&`: Close the current window.

- `%`: Split the screen vertically (left and right).
- `"`: Split the screen horizontally (top and bottom).
- `Arrow Keys`: Navigate between the split panes.
- `x`: Close the active pane.
