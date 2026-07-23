
## changing system hostname (hostnamectl)

To change your Linux system hostname using `hostnamectl`, check your current name, set the new name, and update the host file.

Steps to Change Hostname: 

- Check current name: Run `hostnamectl` to view the active static, transient, and pretty hostnames.
- Set new name: Run `sudo hostnamectl set-hostname <new-name>` to update it immediately and permanently across reboots.
- Update hosts file: Open `/etc/hosts` using a text editor (`sudo nano /etc/hosts`) and replace the old hostname with your `<new-name>` next to the `127.0.1.1` or `127.0.0.1` line.
- Verify: Open a new terminal window or log back in to see the updated prompt.
