
## tune system performance (tuned, nice and renice)

You can tune Linux system performance using tuned for automated profile management and nice/renice for manual CPU process prioritization. 

### Tuned (`tuned`)

tuned is a daemon that actively monitors your system and tunes system settings dynamically based on a chosen profile. 

- **Installation**: Install it via your package manager, such as sudo dnf install tuned or sudo apt install tuned.
- **Activation**: Enable and start the service using sudo systemctl enable --now tuned.
- **Check Active Profile**: Run tuned-adm active to see what profile is currently running.
- **Switch Profile**: Change your behavior profile using tuned-adm profile <profile-name> (e.g., power-saving, throughput-performance, or virtual-host).
- **Recommendation**: Run tuned-adm recommend to let the system suggest the best profile for your hardware.
