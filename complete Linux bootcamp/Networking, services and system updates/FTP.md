
## FTP

FTP (File Transfer Protocol) in Linux is a standard network protocol used to transfer files between a local computer and a server over a network. You can run it via command-line tools (ftp) or set up background daemons (like vsftpd) to turn a Linux machine into a file server.


- Client-Server Model: The server software listens for incoming connections, while the client (ftp command or a GUI tool like FileZilla) initiates the connection to upload or download files.
- Lack of Encryption: Standard FTP sends passwords and data in plain text. It is unsafe for use over the open internet.
- Secure Alternatives: Modern Linux systems generally prefer SFTP (Secure File Transfer Protocol, running over SSH) or SCP for encrypted and secure file sharing.

### common commands: 

Once you connect to a remote host using `ftp [hostname]`, you can use these interactive commands:

- `open [host]`: Connect to a remote FTP server.
- `ls`: List files in the current remote directory.
- `pwd`: Show the current directory on the remote server.
- `cd [dir]`: Change directory on the remote server.
- `get [file]`: Download a file from the server to your local machine.
- `put [file]`: Upload a file from your local machine to the server.
- `bye` or `quit`: Close the session.
