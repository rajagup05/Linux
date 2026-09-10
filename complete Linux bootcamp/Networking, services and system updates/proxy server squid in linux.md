
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
