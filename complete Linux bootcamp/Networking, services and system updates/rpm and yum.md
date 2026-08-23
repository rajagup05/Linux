
## rpm and yum

In Red Hat-based Linux systems, RPM is a low-level tool that handles individual .rpm files, while YUM is a higher-level tool that downloads and updates software from repositories while fixing dependencies automatically.

### RPM Package Manager Commands

RPM works offline with single package files, but it cannot resolve missing software dependencies on its own.

- `rpm -ivh package.rpm`: Install a local package with progress bars.
- `rpm -Uvh package.rpm`: Upgrade an existing package.
- `rpm -Uvh package.rpm`: Upgrade an existing package.
- `rpm -qa`: Query and list all installed packages on the system.
- `rpm -qi package_name`: Show detailed info about an installed package.


### YUM Package Manager Commands

YUM connects to local or remote software repositories to manage system updates and automatically pull required dependencies.

- `sudo yum update`: Update all installed system packages.
- `sudo yum install package_name`: Install a package and its dependencies.
- `sudo yum remove package_name`: Remove a package from the system.
- `yum repolist`: List all enabled software repositories.
- `yum search keyword`: Search for packages in the repositories.
