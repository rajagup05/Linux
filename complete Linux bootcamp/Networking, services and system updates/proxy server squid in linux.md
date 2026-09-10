
## proxy server squid in linux

You can set up a caching and filtering proxy server on Linux using Squid Proxy, which listens on port 3128 by default. 

### Installation

- Update your system package list: `sudo apt update -y`
- Install the Squid package: `sudo apt install squid -y`
- Start and enable the service:

```
sudo systemctl start squid
sudo systemctl enable squid
```

### Basic Configuration

- Open the main configuration file with a text editor: `sudo nano /etc/squid/squid.conf`
- Locate the http_access rules and define which IP addresses can access your proxy using Access Control Lists (ACLs).
- Change the default port (http_port 3128) if needed.
- Test your configuration file for syntax errors: `sudo squid -k parse`
- Restart the Squid service to apply changes: `sudo systemctl restart squid`
