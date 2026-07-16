
## systemctl

The systemctl command is the primary command-line utility used to control, manage, and inspect the systemd system and service manager on modern Linux distributions. It allows administrators to start or stop processes, configure background applications to run automatically at boot, and troubleshoot system health.

syntax:  `systemctl [options] command [unit_name]`

### 🟢 Managing Current Runtime (Start, Stop, Restart)

- Check status: `systemctl status nginx` (Shows if a service is running, its process ID, and recent log entries).
- Start a service: `sudo systemctl start nginx` (Fires up a stopped background process immediately).
- Stop a service: `sudo systemctl stop nginx` (Kills a running background process immediately).
- Restart a service: `sudo systemctl restart nginx` (Completely stops the service and spins it back up; useful for aggressive configuration rewrites).
- Reload a service: `sudo systemctl reload nginx` (Refreshes config files without dropping active connections or killing live user traffic).

### 🚀 Managing Boot Behavior (Enable, Disable)

- Enable at boot: `sudo systemctl enable nginx` (Creates a symbolic link so the service auto-starts at next boot, but does not start it right now).
- Disable at boot: `sudo systemctl disable nginx` (Removes the link so it won't auto-start, but leaves the currently running process untouched).

### 🔍 System Inspection & Troubleshooting

- List all active services: `systemctl list-units --type=service`

### ⚡ System Power States

- Reboot the machine: `systemctl reboot`
- Power down the machine: `systemctl poweroff`
