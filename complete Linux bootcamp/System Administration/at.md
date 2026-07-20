
## at command in Linux

The at command in Linux is a command-line utility used to schedule a task or script to run exactly once at a specific time in the future. Unlike cron, which is built for recurring jobs (e.g., every midnight), at is optimized for temporary automation.

### Basic Syntax & Interactive Mode

The standard syntax is `at [time]`. When you run this, it drops you into an interactive prompt (`at>`) where you can type your commands.

- Type your commands sequentially:
```
  at> /home/user/backup.sh
  at> echo "Backup complete" > /tmp/log.txt
```
- Press Ctrl + D to save and exit. You will see a confirmation with a unique Job ID.

### other examples: 

- `at now + 15 minutes`: Runs 15 minutes from right now.
- `at now + 2 hours`: Runs 2 hours from right now.
- `at 04:15 PM`: Runs at 4:15 PM today (or tomorrow if that time passed).
- `at 11:30 AM Jul 31`: Runs at the exact time and calendar date.
- `at midnight`: Runs at 12:00 AM tonight.

