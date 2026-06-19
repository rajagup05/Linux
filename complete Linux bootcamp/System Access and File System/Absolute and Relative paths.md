
## Absolute and Relative paths

An absolute path specifies the complete location of a file or directory starting from the root directory (/), while a relative path specifies the location relative to your current working directory.

### Absolute path

An absolute path is the equivalent of a complete mailing address. No matter where you are currently standing in the Linux filesystem, an absolute path always tracks down the exact same location.

- **Syntax**: Always begins with `/`.
- **Examples**:
  - `/etc/ssh/sshd_config` (A configuration file)
  - `/var/log/nginx/access.log` (A web server log file)
  - `/home/ubuntu/Documents/report.pdf` (A file in a user's home directory)
 
### Relative Paths

A relative path relies heavily on your current position in the terminal. It uses your current working directory as the reference point to pinpoint target files.

To build relative paths, Linux relies on specific shorthand symbols:

- `.` (Single dot): Represents the current directory.
- `..` (Double dot): Represents the parent directory (one level up).
- `~` (Tilde): Represents the current user's home directory (e.g., `/home/username`).







