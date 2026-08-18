
## ssh keys access remote server without password 

To access a remote Linux server via SSH without a password, generate an SSH key pair on your local machine using ssh-keygen, and copy the public key to the remote server using ssh-copy-id username@remote_host, entering your password one final time to complete the setup.

### Step 1: Generate the SSH Key Pair

- Open the terminal on your local computer.
- Run the key generator command: `ssh-keygen -t rsa -b 4096`
- Press Enter to accept the default file location (`~/.ssh/id_rsa`).
- Press Enter twice when prompted for a passphrase to leave it completely empty for passwordless access.

