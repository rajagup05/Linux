
## creating local repositories yum server

To create a local YUM/DNF repository server in Linux, you need to gather the RPM packages, generate repository metadata using createrepo, and share the directory via an HTTP server like Apache (httpd). This setup allows offline or air-gapped client machines on your local network to install software quickly without internet access.

### Step 1: Install Required Utilities

You will need the createrepo tool to generate repository XML metadata and the Apache HTTP server (httpd) to host the files.

- Run the following command on your designated repository server: `sudo dnf install -y createrepo httpd yum-utils`

### Step 2: Prepare the Package Directory

You must host your packages inside Apache's public document root so clients can download them over the network.

- Create a dedicated directory structure for your custom packages: `sudo mkdir -p /var/www/html/repos/local-x86_64`
- Copy your collection of custom .rpm files into this directory. If you want to download and mirror an entire public upstream repository instead, use the reposync utility: `sudo reposync --download-metadata --repo=baseos -p /var/www/html/repos/`
