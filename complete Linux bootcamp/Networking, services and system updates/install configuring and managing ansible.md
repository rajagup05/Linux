
## install configuring and managing ansible 

### Installing

Ansible installs on a central computer called the control node. Target computers are managed nodes and only need Python and SSH.

- Update your system package list: `sudo apt update`
- Add the official Ansible repository: `sudo apt-add-repository ppa:ansible/ansible`
- Install Ansible using the package manager: `sudo apt install ansible -y`
- Check that the installation works: `ansible --version`

### Configuration

Configuration happens through the inventory file and secure shell keys.

- Open or create the host inventory file located at `/etc/ansible/hosts`.
- Add your managed node IP addresses under a group name:

```
[app_servers]
192.168.1.50
192.168.1.51
```

