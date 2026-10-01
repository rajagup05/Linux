
## logical volume management (LVM)

Logical Volume Manager (LVM) is a highly flexible storage management framework for the Linux kernel that abstracts physical storage devices. Unlike traditional disk partitioning—which creates rigid, contiguous blocks of fixed sizes—LVM allows you to pool multiple hard drives or partitions into a single, cohesive storage pool and dynamically allocate space as needed.

### The Three Layers of LVM

LVM operates using three primary abstractions built on top of physical hardware:

    +---------------------------------------------------+
    
    |         Logical Volumes (LV) / File Systems       |  <- (e.g., /root, /home)
    +---------------------------------------------------+
    
    |                  Volume Group (VG)                |  <- Combined Storage Pool
    +---------------------------------------------------+
    
    | Physical Volume (PV) | Physical Volume (PV)       |  <- Initialized Disks
    +----------------------+----------------------------+
    
    |  /dev/sda1 (SSD)     |  /dev/sdb (HDD)            |  <- Raw Hardware
    +---------------------------------------------------+

- **Physical Volumes** (PV): The raw storage devices (such as an entire hard drive, a standard partition, or an external LUN) initialized for LVM use. Initializing a PV writes LVM metadata headers to the device.
- **Volume Groups** (VG): The master storage pool. You combine one or more Physical Volumes into a Volume Group, creating a large, single reservoir of storage.
- **Logical Volumes** (LV): The virtual partitions carved out of a Volume Group. These behave exactly like traditional physical partitions; you format them with a filesystem (such as ext4 or XFS) and mount them to your system.

### What Happens Under the Hood?

LVM slices Physical Volumes into uniform chunks called Physical Extents (PE) (typically 4 MB by default). When you create or expand a Logical Volume, LVM allocates a collection of these PEs to it. Because these extents can be mapped from anywhere inside the Volume Group, a Logical Volume does not need to be contiguous and can safely span across entirely different physical hard drives.

