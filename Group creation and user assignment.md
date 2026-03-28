
## Group creation and user assignment


a. **Create a group named `admin_users` across all App servers (server A B & C) within the Datacenter. **

- used `ssh user1@server1` to connect to the Server 1.
- used `sudo groupadd admin_users` to create a group.
- used `grep admin /etc/groups` to see if group is created and this was the output: `admin_users:x:1001:`

b. Add the user mohammed into the `admin_users` group on all App servers. If the user doesn't exist, create it as well.

- used sudo useradd -G admin_users user1 to add this user into existing group.
- used grep user1 /etc/passwd to see if user is added to group and this is output: user1:x:1001:1002::/home/user1:/bin/bash

