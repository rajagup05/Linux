
## crontab

The crontab command in Linux is a time-based job scheduler used to create, edit, view, and manage automated background tasks (known as cron jobs). It allows you to automatically run scripts, backups, or system updates at specific times, dates, or intervals without any manual effort.

### commands: 

- `crontab -e` : Edits or creates your personal crontab file using your terminal's default text editor.
- `crontab -l` : Lists all currently scheduled cron jobs for your logged-in user.

### Crontab Syntax: 

*  *  *  *  *    /path/to/command \
│  │  │  │  │ \
│  │  │  │  └─── Day of the Week (0 - 6) (0 is Sunday, or use names like Sun-Sat) \
│  │  │  └────── Month of the Year (1 - 12) (or names like Jan-Dec) \
│  │  └───────── Day of the Month (1 - 31) \
│  └──────────── Hour of the Day (0 - 23) \
└─────────────── Minute of the Hour (0 - 59) \

### Special Character Operators

- `*` (Asterisk) : Matches every possible value in that specific field.
- `,` (Comma) : Separates a list of discrete multiple values (e.g., 1,3,5 in the weekday field means Mon, Wed, Fri).
- `-` (Hyphen) : Defines an inclusive range of numbers (e.g., 9-17 in the hour field means 9 AM through 5 PM).
- `/` (Forward Slash) : Specifies step intervals (e.g., */10 in the minute field runs the task exactly every 10 minutes).

### Examples

- Every minute: `* * * * * /home/user/script.sh`
- Every 15 minutes: `*/15 * * * * /home/user/script.sh`
- Every day at 3:30 AM: `30 3 * * * /home/user/backup.sh`
- Every Sunday at midnight: `0 0 * * 0 /home/user/cleanup.sh`
- Weekday business hours (Every hour, 9 AM - 5 PM, Mon-Fri): `0 9-17 * * 1-5 /home/user/report.sh`

### Time-Saving Shortcuts

Instead of using five distinct time fields, you can alternatively use these built-in system strings:

- `@daily` : Runs a job exactly once a day at midnight (`0 0 * * *`).
- `@weekly` : Runs a job once a week on Sunday at midnight (`0 0 * * 0`).
- `@monthly` : Runs a job on the first minute of every single month (`0 0 1 * *`).








