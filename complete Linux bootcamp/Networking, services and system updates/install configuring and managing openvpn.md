
## install configuring and managing openVPN

### Installation

- Log in to your Linux server with root privileges.
- Download the installation script by running: `curl -O https://raw.githubusercontent.com/angristan/openvpn-install/master/openvpn-install.sh`
- Make the script executable: `chmod +x openvpn-install.sh`
- Run the script and follow the interactive on-screen prompts to configure your public IP, port (default is 1194), and DNS preferences: `./openvpn-install.sh`
