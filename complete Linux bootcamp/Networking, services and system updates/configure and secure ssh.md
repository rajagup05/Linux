
## configure and secure ssh

To configure and secure SSH on Linux, you must enforce key-based authentication, restrict administrative access, and harden the SSH daemon configuration.

Always maintain an active, working SSH session in one terminal window while testing changes in another to avoid locking yourself out.

### Generate and Deploy SSH Keys

Avoid using passwords entirely. Generate a highly secure Ed25519 key pair on your local machine instead of the older RSA algorithm.

- Generate the key pair on your local terminal: `ssh-keygen -t ed25519 -C "your_email@example.com"`
- Copy the public key to your Linux server: `ssh-copy-id -i ~/.ssh/id_ed25519.pub user@your_server_ip`
- Verify the connection works without requiring your system user password: `ssh user@your_server_ip`

### Harden the Configuration File

Open the primary configuration file using a text editor with administrative privileges:

`sudo nano /etc/ssh/sshd_config`

Note: If you are running Ubuntu 24.04/26.04 or newer distributions, it is best practice to create a custom file under `/etc/ssh/sshd_config.d/hardened.conf` instead of editing the main file directly.

Modify or append the following security definitions to match this baseline config:

```
# Disable direct administrative logins. Force users to use sudo.
PermitRootLogin no

# Disable password-based logins entirely to eliminate brute-force vector attacks.
PasswordAuthentication no
PermitEmptyPasswords no

# Enforce public key authentication.
PubkeyAuthentication yes

# Limit the maximum number of failed authentication attempts per connection.
MaxAuthTries 3

# Disconnect inactive or abandoned sessions automatically (300 seconds / 5 minutes).
ClientAliveInterval 300
ClientAliveCountMax 0

# Limit remote shell access to explicitly named users.
AllowUsers your_username
```
