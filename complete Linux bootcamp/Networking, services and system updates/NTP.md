
## NTP (Network Time Protocol)

Network Time Protocol (NTP) is the standard protocol used to synchronize the system clocks of Linux computers over a network. Keeping an accurate system time is critical for log file analysis, database transactions, security certificates, and cron jobs.

### 1. Modern vs. Traditional NTP Daemons

- chronyd (Chrony): The modern standard. Fast, highly accurate, and handles intermittent network connections exceptionally well. (RHEL, CentOS, Fedora, Ubuntu (newer versions))
- ntpd: The classic reference implementation of NTP. Largely replaced by Chrony but still used in specific older setups. (Older Linux distributions)
