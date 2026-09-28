
## customize message of the day

You can customize your Linux Message of the Day (MOTD) by editing /etc/motd for a static message or by using script directories like /etc/update-motd.d/ on Ubuntu and Debian for dynamic information.

### Static MOTD (All Distributions)

- Open the file with root privileges: `sudo nano /etc/motd`
- Delete the current text and type your custom message.
- Save and close the file.

### Dynamic MOTD (Ubuntu / Debian / AWS Linux)

Modern distributions often use a dynamic system that generates information (like disk space or updates) upon login using scripts stored in a directory.

- View the active scripts in the directory: `ls -la /etc/update-motd.d/`
- Disable any default message or news section you do not want by removing its execute permissions: `sudo chmod -x /etc/update-motd.d/50-motd-news`
- Create your own custom script inside the directory (naming it with a numerical prefix like 85-custom to control the order): `sudo nano /etc/update-motd.d/85-custom`
- Add your desired script content, make it executable, and test: `sudo chmod +x /etc/update-motd.d/85-custom`
