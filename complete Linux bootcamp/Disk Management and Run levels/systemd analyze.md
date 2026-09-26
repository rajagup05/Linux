
## systemd analyze 

The systemd-analyze command is a built-in Linux utility used to profile, analyze, and debug system boot performance. It helps you find which services are slowing down your boot sequence, check configuration files for syntax errors, and inspect service security settings.

### Commands

#### 1. Get an Overview of Boot Time

Running the command without any options shows how long your system took to reach a fully usable state, split into kernel, initrd, and userspace durations.

`systemd-analyze`

Output Example: `Startup finished in 1.21s (kernel) + 3.42s (initrd) + 25.11s (userspace) = 29.74s`

#### 2. Find Slowest-Starting Services (blame)

To see a list of all running units sorted by how long they took to initialize, use the blame subcommand.

`systemd-analyze blame`

#### 3. Inspect the Critical Path (critical-chain)

This command maps out the exact chain of time-critical dependencies that directly impact when your system finishes booting.

`systemd-analyze critical-chain`

You can also pinpoint a specific service to see what it is waiting on:

`systemd-analyze critical-chain nginx.service`

#### 4. Generate a Graphical Bootchart (plot)

You can export the entire boot timeline into an SVG graphic. This creates a visual breakdown of when every single service started and stopped initializing.

`systemd-analyze plot > boot_chart.svg`

#### 5. Verify Unit File Syntax (verify)

Before restarting or enabling a custom systemd service, you can scan it for configuration errors or typos without loading it into the manager.

`systemd-analyze verify /etc/systemd/system/my-app.service`

#### 6. Analyze Service Security Posture (security)

This subcommand assigns a security score (0.0 to 10.0) to a service based on its sandbox settings, helping you see where you can harden access.

`systemd-analyze security nginx.service`
