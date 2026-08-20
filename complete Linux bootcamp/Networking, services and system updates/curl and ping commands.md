
## curl and ping commands

In Linux, ping and curl are essential network troubleshooting utilities, but they operate at entirely different layers of the network stack. ping verifies raw device reachability by sending low-level ICMP echo requests, whereas curl transfers data and interacts with application layer protocols like HTTP, HTTPS, and FTP.

### The `ping` Command

The ping command is the first diagnostic step to check if a remote server is alive and responding. In Linux, ping will run indefinitely until you stop it manually using `Ctrl + C`.

#### Examples:

- Test basic connectivity to a domain or IP address: `ping google.com`
