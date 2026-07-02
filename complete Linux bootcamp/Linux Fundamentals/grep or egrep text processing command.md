
## grep/egrep text processing command

The grep (Global Regular Expression Print) command in Linux is a foundational text-processing utility used to search files or standard input for lines matching a specified pattern. The egrep utility is a shortcut for grep -E, which enables Extended Regular Expressions (ERE) to support complex regex syntax without needing backslash escapes.

`egrep` is generally used as Logical OR (`|`), eg. `egrep "error|warning|critical" /var/log/nginx/error.log`

### syntax: 

- `grep [OPTIONS] "PATTERN" [FILE...]`
- `egrep [OPTIONS] "PATTERN" [FILE...]`

### `grep` options:

- `-i` : Ignores text letter-casing (case-insensitive matching).
- `-v` : Inverts the search to output lines that do not match the pattern.
- `-n` : Displays the matching line numbers alongside the text.
- `-c` : Counts and prints only the total number of matching lines.
- `-r` : Recursively searches all files inside a directory and its subdirectories.
- `-w` : Matches the exact whole word only, preventing partial matches within larger words.
- `-o` : Prints only the exact matching text segment instead of the entire line.

### examples

- `grep "failed" /var/log/syslog`: Search for a specific word inside a file
- `grep -in "error" /var/log/auth.log`: Find the word "error" regardless of casing (e.g., Error, ERROR, eRrOr) and show where it is
- `grep -v "^#" /etc/fstab`: Filter out comments or configuration lines starting with # to read clean files
- `grep -E "error|warning|critical" /var/log/nginx/error.log`: Using `grep -E` allows you to look for several words simultaneously without escaping the pipe character
- `grep -r "DatabaseConnection" /var/www/html/`: Find every mention of a string inside a full project directory tree
- `grep "[0-9]\{4\}" data.txt`: Search for lines containing a specific pattern pattern sequence, such as a 4-digit number or `egrep "[0-9]{4}" data.txt`
- `ps aux | grep "systemd"`: Check if a specific system service process is currently running
- `netstat -tuln | grep ":80"`: Filter active network connections for a specific port
