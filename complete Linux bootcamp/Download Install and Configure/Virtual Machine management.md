
## Virtual Machine management

Oracle VM VirtualBox provides comprehensive virtual machine (VM) management via its graphical VirtualBox Manager and its command-line tool VBoxManage. It allows users to create, configure, clone, snapshot, and network multiple guest operating systems from a single host machine.

### Core management options

- **Creation & Setup**: Use the New wizard to define machine names, assign CPU/RAM, create virtual hard disks, and attach OS installation media (ISO files).
- **State Controls**: Start, pause, reset, save state, or power off guests with single clicks in the Machines list.
- **Snapshots**: Capture the exact state of a VM before making risky changes. You can revert to these snapshots later if the OS breaks.
- **Cloning**: Duplicate existing VMs to save time on setup. You can perform a full clone or a linked clone that shares the base disk to save storage space.
- **Groups**: Organize numerous VMs into folders or nested hierarchies to apply bulk actions like start, shutdown, or power-off.

### Resource Integrations and tuning

- **System Settings**: Adjust allocations for Processor, RAM, and Video Memory in the VM's Settings panel.
- **Shared Folders & Clipboard**: Enable bidirectional drag-and-drop, shared clipboards, and shared folders between your physical host and virtual guest.
- **Network Bridging**: Change network settings to NAT or Bridged Adapter so your VM can share your local connection or appear as an independent device on your local network.
- **Guest Additions**: Install this software package inside the guest OS to unlock auto-resizing screens, seamless mouse integration, and improved 3D performance.
