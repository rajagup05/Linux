
## SCP

In Linux, scp stands for Secure Copy Protocol. It is a command-line utility used to securely copy files and directories between different computers over a network.

Because scp relies on SSH (Secure Shell) for data transfer, all transferred data, including passwords, is fully encrypted and protected from interception.

- Local to Remote: Copy files from your current computer to a server.
- Remote to Local: Download files from a server to your current computer.
- Remote to Remote: Transfer files directly between two separate remote servers.

### syntax

The standard syntax always places the source (where the file is) first, followed by the destination (where the file is going): `scp [OPTIONS] [SOURCE] [DESTINATION]`

### examples:

- Upload a local file to a remote server: `scp document.txt username@remote_ip:/home/username/destination_folder/`
- Download a file from a remote server to your local machine: `scp username@remote_ip:/home/username/server_file.txt /local/folder/`
- Copy an entire directory (folder): `scp -r /local/folder/ username@remote_ip:/home/username/destination/`
