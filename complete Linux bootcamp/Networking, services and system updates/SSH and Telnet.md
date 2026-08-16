
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
