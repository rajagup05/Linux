
## System run levels (0 - 6)

In Linux, a runlevel is a preset operating state that determines which system services and processes are automatically started. Historically managed by the SysV init system, modern Linux distributions have mostly transitioned to systemd, which replaces runlevels with targets.

- `0` (Halt / Shut down) : Shuts down the system completely. Never set this as your default.

- `1` (Single-User Mode): Used for maintenance and troubleshooting. No network services are started, and only the root user can log in.
- `2` (Multi-User Mode (No NFS)): Multi-user mode without network file sharing (NFS). On Debian/Ubuntu systems, this is often identical to runlevel 5.

- `3` (Multi-User Mode (CLI)): Full multi-user command-line interface (text mode) with networking. Standard operating state for most Linux servers.
- `4` (User-Defined / Custom): Generally unused and customizable for specific administrative needs.
- `5` (Multi-User Mode (GUI)): Identical to runlevel 3, but automatically loads a display manager for a graphical user interface (GUI). Standard for desktop systems.

- `6` (Reboot): Reboots the computer. Never set this as your default.

### Commands

#### Checking your current state:

- Traditional: `runlevel`
- Modern systemd: `systemctl get-default`
