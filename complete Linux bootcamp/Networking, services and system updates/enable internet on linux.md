
## enable internet on linux

To enable internet on a Linux virtual machine, turn off the VM and open your hypervisor's network settings (such as VirtualBox or VMware). Change the network adapter mode to NAT for an instant shared connection, or Bridged Adapter to connect directly to your physical router, then boot the VM and start the network interface.

### Configure Hypervisor Network Settings

- Open your virtualization software and select your Linux VM.
- Open Settings and go to the Network tab.
- Enable Network Adapter 1.
- Select an attachment type:
  - NAT: Shares the host computer's internet connection automatically (easiest option).
  - Bridged Adapter: Connects the VM directly to your local physical network or Wi-Fi router so it gets its own unique IP address.
- Check that Cable Connected is ticked, then save and start your VM.
