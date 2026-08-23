
## wget command

`wget` is a free, command-line utility used for downloading files from the internet. It operates non-interactively in the background, supports protocols like HTTP, HTTPS, and FTP, and can gracefully handle network interruptions by automatically resuming failed downloads.

### 🛠️ Installation

If your system throws a `wget: command not found` error, you can install it using your distribution's package manager:

- **Ubuntu / Debian**: `sudo apt install wget`
- **CentOS / RHEL / Fedora**: `sudo dnf install wget`

### Syntax

- `wget [options] [URL]`

### examples

- Downloads a file directly to your current directory: `wget https://example.com/file.zip`
- Saves the downloaded file under a new filename: `wget -O custom_name.zip https://example.com/file.zip`
- Saves the file into a specific directory: `wget -P /path/to/folder/ https://example.com/file.zip`
- Resumes a partially completed or broken download: `wget -c https://example.com`
- Limits download speed to prevent hogging bandwidth: `wget --limit-rate=500k https://example.com/file.zip`
- Runs the download in the background (logs to wget-log): `wget -b https://example.com`
