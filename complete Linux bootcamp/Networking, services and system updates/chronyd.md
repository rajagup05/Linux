
## chronyd

chronyd is the background daemon component of the Chrony Project that synchronizes your Linux system clock with Network Time Protocol (NTP) servers, hardware reference clocks, or manual inputs.

- Background Service: Runs continuously to measure and correct system time drift relative to other computers or accurate time sources.
- Handles Disconnections: Performs exceptionally well on virtual machines, laptops, or networks with intermittent connectivity by gracefully adjusting time after suspension or disconnection.
- Dual Role: Can act as an NTP client to pull time from external sources or as an NTP server to distribute time to other machines on a local network.

- Check status: `systemctl status chronyd`
- Start service: `systemctl start chronyd`
- Enable at boot: `systemctl enable chronyd`
- Check time sources: `chronyc sources`
- Check tracking performance: `chronyc tracking`
