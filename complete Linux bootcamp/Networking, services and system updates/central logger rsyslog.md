
## central logger rsyslog

Rsyslog is an open-source, high-performance utility used in Linux for forwarding and receiving log messages across a network. Implementing a centralized logging architecture with Rsyslog involves a Server-Client model where remote systems (Clients) send their local system logs over the network via TCP or UDP (Port 514) to a designated central system (Server).

### Phase 1: Configuring the Central Rsyslog Server

The central logging server must be configured to open network ports and accept incoming logs from other machines. 

- Open the Rsyslog configuration file: `sudo nano /etc/rsyslog.conf`
- Enable Log Reception: Locate the module definitions and uncomment the lines corresponding to your chosen protocol. It is highly recommended to enable TCP for reliable log delivery.

```
# Provides UDP syslog reception
module(load="imudp")
input(type="imudp" port="514")

# Provides TCP syslog reception
module(load="imtcp")
input(type="imtcp" port="514")
```

- Define a Dynamic Directory Template (Optional but Recommended): By default, the server mixes remote logs into its own /var/log files. To isolate incoming logs by the host that sent them, append a dynamic template rule at the bottom of /etc/rsyslog.conf:

```
$template RemoteLogs,"/var/log/remote/%HOSTNAME%/%PROGRAMNAME%.log"
*.* ?RemoteLogs
& stop
```
- Save the file and restart the service: `sudo systemctl restart rsyslog`
- Verify the server is listening: `sudo ss -tulnp | grep 514`
