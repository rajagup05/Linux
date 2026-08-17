
## SSH and Telnet

SSH (Secure Shell) and Telnet are network protocols used to connect to and manage remote Linux systems via a command-line interface. SSH is the modern, secure standard that encrypts all traffic, whereas Telnet is an obsolete, insecure protocol that transmits data in plain text.

### Comparison

    Feature        |   SSH (Secure Shell)                 |     Telnet 
    ___________________________________________________________________________________________________
    Security          Encrypted traffic (Secure)             Plain text (Insecure)
    Default Port      Port 22                                Port 23
    Authentication    Passwords & Public Key Pairs           Passwords only
    File Transfer     Supported natively via SFTP/SCP        Not supported
    Current Use       Standard for production Linux servers   Legacy devices and network port testing

### How to Use SSH in Linux

SSH encrypts your login credentials and commands, making it safe for public internet connections.

- Basic Connection: `ssh username@remote_ip_address`
- Connect Using a Specific Port: `ssh username@remote_ip_address -p 2222`
- Connect Using an SSH Key (No Password): `ssh -i /path/to/private_key username@remote_ip_address`
