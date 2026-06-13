
## Access Linux via PUTTY or SSH

To access a Linux system via SSH or PuTTY, you need the remote system's IP address, a valid username, and a password (or SSH key).

### Method1: Connecting via PUTTY (Windows)

PuTTY is a free, standalone application used to connect to remote servers from Windows.

- **Download and Launch**: Download PuTTY from its official site and open the application.
- **Enter Connection Details**:
  - `Host Name` (or `IP address`): Type your Linux server's IP address (e.g., 192.168.1.50).
  - `Port`: Keep the default value 22.
  - `Connection type`: Select SSH.
- **Save Session (Optional)**: Type a name in Saved Sessions and click Save so you do not have to type the IP address next time.
- **Connect**: Click Open at the bottom of the window.Accept Security Warning: A pop-up will appear during your very first connection asking to trust the host key. Click Accept or Yes.
- **Log In**: A black terminal screen will appear. Type your Linux username and press Enter. Then type your password (the characters will not show on the screen) and press Enter.
