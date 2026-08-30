
## Mail Transfer Agent

A Mail Transfer Agent (MTA) in Linux is software responsible for sending and receiving emails across networks using the Simple Mail Transfer Protocol (SMTP).

### working

- Acceptance: Receives incoming messages from a Mail User Agent (MUA, like Thunderbird) or another MTA.
- Routing: Looks up DNS MX (Mail Exchange) records to determine the correct destination server.
- Queueing: Stores outgoing messages locally in a queue if the destination server is unreachable, retrying delivery later.
- Delivery: Hands off the message to a local Mail Delivery Agent (MDA) for local users or forwards it to an external MTA.

