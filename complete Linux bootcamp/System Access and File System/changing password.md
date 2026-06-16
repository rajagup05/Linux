
## changing password

In Linux, you can change your password using the terminal with the passwd command. To change your own password, simply type passwd, enter your current password, and type the new one twice. To change another user's password, you will need administrative privileges and should use sudo passwd username.

### For the Current user

- Open your terminal.
- Type the following command and press Enter: `passwd`
- You will be prompted to type your current UNIX password. (Note: For security, no characters will appear on the screen as you type).
- Enter your new password, press Enter, and re-type it to confirm

### For Different user

f you have root or sudo privileges, you can change any user's password without needing their current one.

- Open your terminal.Type the following command (replace username with the actual account name) and press Enter: `sudo passwd username`
- You will be asked to enter your own administrative password.
- Next, type the new password for that specific user and confirm it.
