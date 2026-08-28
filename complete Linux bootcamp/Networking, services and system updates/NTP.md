
## NTP (Network Time Protocol)

Network Time Protocol (NTP) is the standard protocol used to synchronize the system clocks of Linux computers over a network. Keeping an accurate system time is critical for log file analysis, database transactions, security certificates, and cron jobs.

### 1. Modern vs. Traditional NTP Daemons

- chronyd (Chrony): The modern standard. Fast, highly accurate, and handles intermittent network connections exceptionally well. (RHEL, CentOS, Fedora, Ubuntu (newer versions))
- ntpd: The classic reference implementation of NTP. Largely replaced by Chrony but still used in specific older setups. (Older Linux distributions)


### 2. How to Manage Time and Check NTP Status

Regardless of which daemon runs in the background, you can use the unified timedatectl command to check your NTP synchronization status:

`timedatectl status`


### 3. Configuring Chrony (Modern Standard)

If you are running a modern distribution, Chrony is the recommended choice.

- Installation:

```
sudo apt install chrony        # Debian / Ubuntu
sudo dnf install chrony        # RHEL / Rocky Linux / Fedora
```

- Configuration File: `/etc/chrony.conf` (or `/etc/chrony/chrony.conf`)
- Key Command to Check Peers: `chronyc sources -v`

### 4. Configuring Classic NTP (ntpd)

