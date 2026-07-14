
## talking to users

In Linux, you can communicate with other logged-in users directly through the terminal using commands like who (to find users), write (to message a specific user), and wall (to broadcast a message to everyone).

### 1: Find Logged-In Users (who, w)

Before sending a message, check who is currently active and see their terminal line (tty or pts).

$ `who`

output: 

```
john     pts/0        2026-07-14 10:00 (:0)
mary     pts/1        2026-07-14 11:15 (192.168.1.50)
```

### 2: Talk to a Specific User (write)

The write command copies lines from your terminal directly to another user's open terminal screen.

- Start the session by targeting the user's name: $ `write john`
- Type your message. Every time you press Enter, the line appears on their screen.
- End the session by pressing Ctrl + D (sends an EOF marker) or Ctrl + C.

### 3: Message Everyone Simultaneously (wall)

The wall (write all) command is typically used by system administrators to broadcast urgent or planned maintenance details to all active sessions.

- quick broadcast: $ `wall "The server will reboot in 10 minutes."`
- Multi-line Interactive Broadcast:Type `wall` and hit `Enter`, type out your message, then press `Ctrl + D` to send.


