
## web server apache http

The Apache HTTP Server is one of the most widely used open-source web servers for hosting websites and web applications on Linux systems. It forms a core component of the highly popular LAMP (Linux, Apache, MySQL, PHP) tech stack. 

### package names

- **Ubuntu / Debian / Mint**: Package name is `apache2`.
- **RHEL / CentOS / Fedora / Rocky Linux**: Package name is `httpd`.

### Installation

#### 1. Debian / Ubuntu Systems

```
# Update local package indexes
sudo apt update

# Install Apache
sudo apt install apache2

# Allow web traffic through the firewall (if using UFW)
sudo ufw allow 'Apache'
```

#### 2. RHEL / Rocky Linux / Fedora / CentOS Systems

```
# Update local package indexes
sudo dnf update   # Use 'yum' on older systems

# Install Apache
sudo dnf install httpd

# Allow web traffic through the firewall (Firewalld)
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --permanent --add-service=https
sudo firewall-cmd --reload
```

### Management commands

Linux utilizes systemctl to control the background service:

    Action                    Ubuntu / Debian Command          RHEL / Fedora / Rocky Command
    
    start server            sudo systemctl start apache2        sudo systemctl start httpd
    Stop Server             sudo systemctl stop apache2         sudo systemctl stop httpd
    Restart Server          sudo systemctl restart apache2      sudo systemctl restart httpd
    Enable on Boot          sudo systemctl enable apache2       sudo systemctl enable httpd
    Check Status            sudo systemctl status apache2       sudo systemctl status httpd

