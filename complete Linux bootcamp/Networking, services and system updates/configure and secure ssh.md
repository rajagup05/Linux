
## configure and secure ssh

To configure and secure SSH on Linux, you must enforce key-based authentication, restrict administrative access, and harden the SSH daemon configuration.

Always maintain an active, working SSH session in one terminal window while testing changes in another to avoid locking yourself out.

### Generate and Deploy SSH Keys

Avoid using passwords entirely. Generate a highly secure Ed25519 key pair on your local machine instead of the older RSA algorithm.

- Generate the key pair on your local terminal: `ssh-keygen -t ed25519 -C "your_email@example.com"`
- Copy the public key to your Linux server: `ssh-copy-id -i ~/.ssh/id_ed25519.pub user@your_server_ip`
- Verify the connection works without requiring your system user password: `ssh user@your_server_ip`
