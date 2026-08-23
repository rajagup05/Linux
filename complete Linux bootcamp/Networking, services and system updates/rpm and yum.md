
## rpm and yum

In Red Hat-based Linux systems, RPM is a low-level tool that handles individual .rpm files, while YUM is a higher-level tool that downloads and updates software from repositories while fixing dependencies automatically.

### RPM Package Manager Commands

RPM works offline with single package files, but it cannot resolve missing software dependencies on its own.

- `rpm -ivh package.rpm`: Install a local package with progress bars.
- `rpm -Uvh package.rpm`: Upgrade an existing package.
- `rpm -Uvh package.rpm`: Upgrade an existing package.
- `rpm -qa`: Query and list all installed packages on the system.
- `rpm -qi package_name`: Show detailed info about an installed package.
