
## ssh keys access remote server without password 

To access a remote Linux server via SSH without a password, generate an SSH key pair on your local machine using ssh-keygen, and copy the public key to the remote server using ssh-copy-id username@remote_host, entering your password one final time to complete the setup.

### Step 1: Generate the SSH Key Pair

- Open the terminal on your local computer.
- Run the key generator command: `ssh-keygen -t rsa -b 4096`
- Press Enter to accept the default file location (`~/.ssh/id_rsa`).
- Press Enter twice when prompted for a passphrase to leave it completely empty for passwordless access.

### Step 2: Copy the Public Key to the Remote Server

Send your public key to the remote server by running this command (replace username and remote_host with your actual login and server IP/domain):

`ssh-copy-id username@remote_host`

- Enter your remote account's password one last time when prompted.
- This automatically appends your public key to the remote user's `~/.ssh/authorized_keys` file.

### Step 3: Connect Without a Password

`ssh username@remote_host`
