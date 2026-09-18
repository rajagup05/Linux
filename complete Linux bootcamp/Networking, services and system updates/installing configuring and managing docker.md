
## installing configuring and managing docker

Docker streamlines application deployment by isolating software inside lightweight containers.

### Phase 1: Installing Docker

```
# For Ubuntu/Debian
sudo apt-get remove docker docker-engine docker.io containerd runc
# For RHEL/Rocky Linux
sudo dnf remove docker docker-client docker-client-latest docker-common docker-latest docker-latest-logrotate docker-logrotate docker-engine
```

### Phase 2: Essential Post-Installation & Configuration

#### 1. Manage the Systemd Service

- Enable and verify Docker on system boot:

```
sudo systemctl enable --now docker
sudo systemctl status docker
```

#### 2. Run Docker Without Sudo

Configure a dedicated user group to avoid using sudo for every command:

```
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```

