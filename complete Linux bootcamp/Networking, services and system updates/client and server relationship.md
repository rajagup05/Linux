
## client and server relationship

The client-server model is a computing structure where a client program requests services or data, and a server program on the same or a remote machine processes those requests and sends back a response. In Linux, this architecture forms the backbone of both local system tasks and network operations.

- Client: A program or device (like a web browser, ssh command, or curl) that asks for data.
- Server: A background program (daemon) that listens on a network port for requests and serves data.
- Sockets: Linux treats network and inter-process communication endpoints as socket files, managing connections via standard input/output methods.
