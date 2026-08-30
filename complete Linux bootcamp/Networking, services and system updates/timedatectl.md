
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

To manually modify the clock, you must first disable automatic network time synchronization (NTP), or the command will fail.

- Turn off NTP synchronization: `sudo timedatectl set-ntp false`
- Set both date and time: `sudo timedatectl set-time "YYYY-MM-DD HH:MM:SS"`. Example: `sudo timedatectl set-time "2026-08-29 20:15:00"`
- Set date only (leaves current time intact): `sudo timedatectl set-time "YYYY-MM-DD"`
- Set time only (leaves current date intact): `sudo timedatectl set-time "HH:MM:SS"`


### 4. Enable Automatic NTP Synchronization

To let your system automatically keep the clock accurate using remote network time servers, turn NTP synchronization back on:

`sudo timedatectl set-ntp true`

To view detailed synchronization diagnostics (like the active server name and poll intervals) for systemd-timesyncd, use:

`timedatectl timesync-status`

### 5. Configure the Hardware Clock (RTC)

The hardware clock built into your motherboard can store time in either Coordinated Universal Time (UTC) or Local Time. Maintaining the RTC in UTC is highly recommended for Linux servers and standalone systems to avoid Daylight Saving Time bugs.

- Set the hardware clock to UTC (Recommended): `sudo timedatectl set-local-rtc 0`
- Set the hardware clock to Local Time: `sudo timedatectl set-local-rtc 1`
