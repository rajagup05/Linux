
## process signals in linux

In Linux, process signals are asynchronous software interrupts sent by the kernel, users, or other applications to notify a process that a specific event has occurred. They form a foundational method of Inter-Process Communication (IPC) and are primarily used to manage process life cycles, handle errors, and trigger system actions.

Standard Linux signals are designated by an integer and a symbolic name starting with SIG. You can view a full list on your system by executing kill -l in the terminal.

- `SIGHUP (1)`: Hangup. Sent when a controlling terminal closes. Daemons frequently intercept this to reload their configuration files without shutting down.
- `SIGINT (2)`: Terminal Interrupt. Triggered immediately when a user types `Ctrl + C` in the foreground terminal.
- `SIGQUIT (3)`: Terminal Quit. Similar to SIGINT (triggered by `Ctrl + \`), but it forces the process to dump its core memory before shutting down.
- `SIGKILL (9)`: Forceful Kill. This signal cannot be caught, blocked, or ignored by the application; the kernel terminates the process immediately.
- `SIGSEGV (11)`: Segmentation Fault. Issued by the kernel when a process attempts to read or write to an invalid memory segment that it does not own.
- `SIGTERM (15)`: Termination. The default signal sent by the kill command. It politely requests an application to terminate, allowing it to save states and clean up resources.
- `SIGSTOP (19)`: Forceful Stop. Pauses process execution immediately and cannot be blocked or handled.
- `SIGTSTP (20)`: Terminal Stop. Suspends execution when a user presses `Ctrl + Z`, but unlike SIGSTOP, it can be caught or ignored by the program.
- `SIGCONT (18)`: Continue. Commands a paused or stopped process to resume execution.

examples: 

- Using kill (by PID): Sends a signal using the target's Process ID.

```
kill -15 1234      # Gracefully terminates process 1234 (SIGTERM)
kill -9 1234       # Forcefully terminates process 1234 (SIGKILL)
```
