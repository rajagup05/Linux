
## curl and ping commands

In Linux, ping and curl are essential network troubleshooting utilities, but they operate at entirely different layers of the network stack. ping verifies raw device reachability by sending low-level ICMP echo requests, whereas curl transfers data and interacts with application layer protocols like HTTP, HTTPS, and FTP.

### The `ping` Command

The ping command is the first diagnostic step to check if a remote server is alive and responding. In Linux, ping will run indefinitely until you stop it manually using `Ctrl + C`.

#### Examples:

- Test basic connectivity to a domain or IP address: `ping google.com`
- Limit the packet count so the command stops automatically (e.g., after 4 pings): `ping -c 4 google.com`
- Change the interval between sending packets to speed up the test (e.g., every 0.2 seconds): `ping -i 0.2 google.com`
- Test IPv6 connectivity specifically: `ping6 google.com`

### The `curl` Command

The curl command stands for "Client URL." It is an incredibly powerful tool for transferring data, downloading files, and debugging web services.

#### Examples: 

- Fetch full page content and display it directly in the terminal: `curl https://example.com`
- Fetch HTTP headers only to see if a web server configuration or status code (like 200 OK) is working without downloading the page body: `curl -I https://example.com`
- Download and save a file using its original remote filename: `curl -O https://example.com/file.tar.gz`
- Send a POST request with JSON data to test an API endpoint: `curl -X POST -H "Content-Type: application/json" -d '{"name": "Alice"}' https://example.com`
