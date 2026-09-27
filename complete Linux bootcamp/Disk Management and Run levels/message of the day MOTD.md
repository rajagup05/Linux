
## message of the day (MOTD)

The Linux Message of the Day (MOTD) is a text notice or system status report displayed to users immediately after they log in via the terminal or SSH.

### Where MOTD is Stored

- Static MOTD: Located at /etc/motd, which contains plain text set by the system administrator.
- Dynamic MOTD (Ubuntu/Debian): Generated via scripts run from the /etc/update-motd.d/ directory.

### How to Change Static MOTD

Open or create the file with root privileges:

`sudo nano /etc/motd`

### How to Manage Dynamic MOTD (Ubuntu/Debian)

- Add a custom section: Create an executable script in /etc/update-motd.d/ (for example, 99-custom).
- Disable specific parts: Remove the executable permission from unwanted scripts in that folder:

`sudo chmod -x /etc/update-motd.d/50-motd-news`
