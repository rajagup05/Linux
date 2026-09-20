
## install configuring and managing openVPN

### Installation

- Log in to your Linux server with root privileges.
- Download the installation script by running: `curl -O https://raw.githubusercontent.com/angristan/openvpn-install/master/openvpn-install.sh`
- Make the script executable: `chmod +x openvpn-install.sh`
- Run the script and follow the interactive on-screen prompts to configure your public IP, port (default is 1194), and DNS preferences: `./openvpn-install.sh`

### Configuring and Managing

- **Add a new user/client**: Re-run the script (`./openvpn-install.sh`) and select the option to add a new user, which generates a .ovpn client profile.
- **List clients**: Run `./openvpn-install.sh client list` via CLI mode.
- **Revoke a client**: Run `./openvpn-install.sh client revoke [username]` to immediately disconnect and disable that client profile.
- **Start or check service status (Ubuntu/Debian)**: Use standard system commands like `systemctl start openvpn-server@server.service` or `systemctl status openvpn-server@server.service`.
