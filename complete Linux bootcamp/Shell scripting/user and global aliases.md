
## user and global aliases

In Linux, user-specific aliases are defined in a user's home directory (usually `~/.bashrc` or `~/.bash_aliases`), while global aliases apply to all users and are defined in `/etc/bash.bashrc` or `/etc/profile.d/`.

### 📂 Configuration Locations

- User Aliases: Edit `~/.bashrc` or `~/.bash_aliases`. Affected paths: `~/.bashrc`.
- Global Aliases: Edit `/etc/bash.bashrc` or create a `.sh` file in `/etc/profile.d/`.

### 🛠️ How to Add Them

**For a Single User:**

- Open the file: `nano ~/.bashrc`
- Add the alias: `alias ll='ls -la'`
- Apply changes: `source ~/.bashrc`


**For All Users (Global):**

- Open the global file: `sudo nano /etc/bash.bashrc`
- Add the alias: `alias ll='ls -la'`
- Apply changes: `source /etc/bash.bashrc`
