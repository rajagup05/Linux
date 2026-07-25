
## sos report

An sos report (formerly known as sosreport) is a command-line utility in Linux that collects comprehensive diagnostic data, system logs, configuration files, and hardware details into a single compressed archive. It serves as a standard baseline tool for technical support teams (such as Red Hat, Oracle, or Dell) to analyze system health and troubleshoot operational issues.

### Key Data Collected

- System Logs: Contents of `/var/log` including syslog, boot logs, and application-specific outputs.
- Configurations: Critical files located inside `/etc` (e.g., network settings, service configurations).
- Kernel & Hardware Metrics: Information about the running kernel version, loaded modules, file systems, disk partitioning, and CPU/memory statistics.
- Network Status: Interfaces, IP routing tables, and firewall configurations.
