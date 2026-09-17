
## podman

Podman is a free, open-source, and daemonless container engine designed for Linux that manages OCI-compliant containers, images, and pods without needing a background root service. 

- **Daemonless architecture**: Runs containers as direct child processes instead of relying on a central background service like dockerd.
- **Rootless containers**: Allows standard, unprivileged users to create and manage containers securely.
- **Docker compatibility**: Mirrors the Docker command-line interface, meaning commands like podman run or podman build work identically.
- **Kubernetes ready**: Supports managing pods and generating Kubernetes-style manifests or systemd services. 

### Installation

- **Fedora / RHEL / CentOS**: `sudo dnf install podman`
- **Ubuntu / Debian**: `sudo apt install podman`
- **Arch Linux**: `sudo pacman -S podman`
