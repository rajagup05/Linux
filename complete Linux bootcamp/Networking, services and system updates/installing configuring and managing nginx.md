
## installing configuring and managing nginx

NGINX is a high-performance HTTP web server, reverse proxy, and load balancer. Managing it on Linux requires an understanding of package installation, process management, and server block configurations. 

### 1. Installing NGINX

- For Ubuntu / Debian Systems:

```
sudo apt update
sudo apt install nginx -y
```

### For CentOS / RHEL / Rocky Linux Systems:

```
sudo dnf install epel-release -y
sudo dnf install nginx -y
```

### 2. Managing the NGINX Process

NGINX relies on systemd to manage its background service. Use these essential commands to control its lifecycle

- `sudo systemctl start nginx`:      Starts the NGINX web server immediately.
- `sudo systemctl stop nginx`:       Shuts down the NGINX server.
- `sudo systemctl restart nginx`:    Hard-restarts the service (causes brief downtime).
- `sudo systemctl reload nginx`:     Highly Recommended: Reloads configuration changes without dropping active connections.
- `sudo systemctl enable nginx`:     Configures NGINX to launch automatically during system boot.
- `sudo systemctl status nginx`:     Checks if the server is actively running or experiencing errors.
