
## Access to Linux Systems

You can access a Linux system primarily in two ways: locally via a physical/virtual console or remotely over a network connection. The exact approach depends entirely on your current hardware setup and system requirements.

### Method1: Local access (Console or Desktop)

If you are sitting directly in front of the machine or running Linux inside a virtual machine console:

- `Graphical User Interface (GUI)`: Select your username on the greeting screen, enter your password, and click sign-in. Access the command line by opening the application menu and selecting Terminal or by pressing `Ctrl + Alt + T` on your keyboard.
- `Text-based Virtual Console`: Type your exact case-sensitive username at the login: prompt and press Enter. Type your password—note that Linux will not show placeholder characters (like asterisks) while typing for security. Press Enter again.

### Method2: Remote Access (Command Line)

- `Using macOS or Linux`: Open your built-in terminal window and run the native command:`ssh username@remote_ip_address`
- `Using Windows`: Use native terminal apps or download a free utility like PuTTY. Enter the IP address of the target server, leave the port as 22, and click Open.
