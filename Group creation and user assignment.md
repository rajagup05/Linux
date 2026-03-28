
## Group creation and user assignment


a. **Create a group named `admin_users` across all App servers (server A B & C) within the Datacenter. **

- used `ssh user1@server1` to connect to the Server 1.
- used `sudo groupadd admin_users` to create a group.
- used `grep admin /etc/groups` to see if group is created and this was the output: `admin_users:x:1001:`

b. Add the user mohammed into the `admin_users` group on all App servers. If the user doesn't exist, create it as well.
