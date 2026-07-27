
## screen command in linux

The screen command in Linux is a terminal multiplexer that allows you to start a persistent terminal session and run long-running background processes that remain active even if you disconnect from your server or close your terminal window.

- `Sessions`: A standalone terminal environment running in the background.
- `Detaching`: Leaving a session running in the background while returning to your main shell.
- `Reattaching`: Reconnecting to a running background session to resume your work.

### Basic commands

- Start a regular session: `screen`
- Start a named session: `screen -S <session_name>`
- List active sessions: `screen -ls`
- Reattach to a session: `screen -r <session_name_or_id>`
- Force detach a stale session and reattach: `screen -d -r <session_name>`
- Kill a session from outside: `screen -X -S <session_name> quit`
