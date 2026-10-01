
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
