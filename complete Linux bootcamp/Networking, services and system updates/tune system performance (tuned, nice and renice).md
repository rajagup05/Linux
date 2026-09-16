
## tune system performance (tuned, nice and renice)

You can tune Linux system performance using tuned for automated profile management and nice/renice for manual CPU process prioritization. 

### Tuned (`tuned`)

tuned is a daemon that actively monitors your system and tunes system settings dynamically based on a chosen profile. 

- **Installation**: Install it via your package manager, such as sudo dnf install tuned or sudo apt install tuned.
- **Activation**: Enable and start the service using sudo systemctl enable --now tuned.
- **Check Active Profile**: Run tuned-adm active to see what profile is currently running.
- **Switch Profile**: Change your behavior profile using tuned-adm profile <profile-name> (e.g., power-saving, throughput-performance, or virtual-host).
- **Recommendation**: Run tuned-adm recommend to let the system suggest the best profile for your hardware.

### Nice Command

The nice command launches a new program with a modified scheduling priority, dictating how "nice" a process is to other programs competing for CPU time. 

- **Niceness Range**: Values span from -20 (highest priority, least nice) to +19 (lowest priority, most nice). The default value is 0.
- **Permissions**: Regular users can only increase the nice value (lower the priority, from 0 to 19). Only the root user can assign negative nice values (higher priority).
- **Syntax**: `nice -n [niceness_value] [command]`
- **Example**: Run a heavy backup job with a lower priority so it does not lag the system:`nice -n 10 tar czf backup.tar.gz /large-directory`

### Renice Command

The renice command changes the scheduling priority of an already running process using its Process ID (PID), user name, or group ID. 

- **Syntax**: `renice [niceness_value] -p [PID]`
- **Permissions**: Like nice, regular users can only make their own processes "nicer" (increase the value). Superuser (sudo) permissions are required to increase priority (negative values) or modify other users' processes.
- **Example**: Lower the priority of a running process with PID 1234:`renice -n 5 -p 1234`
- **Example**: Alter all processes belonging to a specific user:`sudo renice 10 -u username`

You can view current nice (NI) values using system monitoring utilities: 

- **Top/Htop**: Look at the `NI` column in real-time.
- **PS Command**: Run `ps -o pid,nice,comm` to list process IDs, niceness, and command names.
