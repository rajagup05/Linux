
## creating local repositories yum server

To create a local YUM/DNF repository server in Linux, you need to gather the RPM packages, generate repository metadata using createrepo, and share the directory via an HTTP server like Apache (httpd). This setup allows offline or air-gapped client machines on your local network to install software quickly without internet access.

### Step 1: Install Required Utilities

You will need the createrepo tool to generate repository XML metadata and the Apache HTTP server (httpd) to host the files.

- Run the following command on your designated repository server: `sudo dnf install -y createrepo httpd yum-utils`

### Step 2: Prepare the Package Directory

You must host your packages inside Apache's public document root so clients can download them over the network.

- Create a dedicated directory structure for your custom packages: `sudo mkdir -p /var/www/html/repos/local-x86_64`
- Copy your collection of custom .rpm files into this directory. If you want to download and mirror an entire public upstream repository instead, use the reposync utility: `sudo reposync --download-metadata --repo=baseos -p /var/www/html/repos/`

### Step 3: Initialize the Repository Metadata

The YUM package manager requires index files to search for dependencies. Generate this metadata by pointing createrepo to your package folder:

`sudo createrepo /var/www/html/repos/local-x86_64`

### Step 4: Configure and Start the HTTP Server

Ensure Apache is serving your repository files to the network.

- Start the Apache service and set it to run automatically on system boot: `sudo systemctl enable --now httpd`
- If your firewall is active, allow incoming HTTP traffic:

```
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --reload
```

### Step 5: Configure Client Machines

- To point client machines to your new local YUM server, log into a client terminal and create a new repository file: `sudo nano /etc/yum.repos.d/local-repo.repo`
- Paste the following configuration, replacing <YOUR_SERVER_IP> with the actual IP address or hostname of your YUM server:

```
[custom-local-repo]
name=Local Network Repository
baseurl=http://<YOUR_SERVER_IP>/repos/local-x86_64/
enabled=1
gpgcheck=0
```

- Clear the package cache and verify that the client recognizes the newly built network repository:

```
sudo yum clean all
sudo yum repolist
```
