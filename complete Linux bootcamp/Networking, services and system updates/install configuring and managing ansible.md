
## install configuring and managing ansible 

### Installing

Ansible installs on a central computer called the control node. Target computers are managed nodes and only need Python and SSH.

- Update your system package list: `sudo apt update`
- Add the official Ansible repository: `sudo apt-add-repository ppa:ansible/ansible`
- Install Ansible using the package manager: `sudo apt install ansible -y`
- Check that the installation works: `ansible --version`
