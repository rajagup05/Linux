
## timedatectl

The timedatectl command is a modern command-line utility used to query and change the system clock, time zone, and Network Time Protocol (NTP) synchronization settings on systemd-based Linux distributions. It replaces the older date and hwclock tools.

### 1. View Current Time Settings

- To display the current local time, universal time (UTC), hardware clock (RTC), time zone, and NTP synchronization status, simply run: `timedatectl`

### 2. Manage Time Zones

To permanently change the system-wide time zone, you first need to find the correct identifier and then apply it.

- List all available time zones: `timedatectl list-timezones`
- Filter for a specific region (e.g., America): `timedatectl list-timezones | grep "America"`
- Set the time zone: `sudo timedatectl set-timezone Region/City` (Example: `sudo timedatectl set-timezone America/New_York`)

### 3. Change Date and Time Manually
