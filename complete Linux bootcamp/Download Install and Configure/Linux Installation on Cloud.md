
## Linux Installation on Cloud

Installing Linux on Google Cloud Platform (GCP) means creating a Virtual Machine (VM) instance in Compute Engine. You can provision a server in minutes using the GCP Console, selecting a Linux distribution (like Ubuntu or Debian), and connecting via browser-based SSH.

### Create the Linux VM Instance

- Log in to your Google Cloud Console.
- In the navigation menu (top-left), click Compute Engine > VM instances.
- Click Create Instance.
- Name & Region: Name your instance and select the region closest to you.Machine Configuration: Choose your machine family (e.g., E2 for general, low-cost computing) and size based on your needs.
- Boot Disk: Click Change.
- Under Public images, select your preferred Linux OS (e.g., Ubuntu, Debian, CentOS) and version.
- Firewall: Check the boxes to Allow HTTP traffic and Allow HTTPS traffic if you plan to host a website.
- Click Create

### Connect to your Linux Instance:

- Once the instance is provisioned, you will see a green checkmark next to its name.
- In the row for your newly created VM, click the SSH button.
- A browser window will open, dropping you directly into the Linux command line

### Update and Install Packages

Once connected, it's best practice to update the package list and install your desired tools. For Ubuntu/Debian, use:

```
sudo apt update
sudo apt upgrade -y
```








