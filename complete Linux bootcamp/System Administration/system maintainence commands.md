
## system maintainence commands 

To perform system maintenance power operations in Linux, you can use the commands `shutdown`, `init`, `reboot`, and `halt`. On modern Linux distributions utilizing systemd, these tools function as wrappers for the primary systemctl control tool.


### 1. The shutdown Command

This is the safest and most flexible command for production environments. It broadcasts warning messages to logged-in users and allows scheduling.

- `sudo shutdown now` — Powers down the machine immediately.
- `sudo shutdown -r now` — Reboots the machine immediately.
- `sudo shutdown +15 "Maintenance starting"` — Schedules a shutdown in 15 minutes and broadcasts a custom warning message.
- `sudo shutdown 23:30` — Schedules a shutdown at a precise time (24-hour format).
