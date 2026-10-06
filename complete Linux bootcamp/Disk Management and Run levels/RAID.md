
## RAID

RAID (Redundant Array of Independent Disks) in Linux combines multiple physical hard drives or SSDs into a single logical storage unit to improve performance, increase capacity, or provide fault tolerance.

### Types

- Software RAID: Managed entirely by the Linux kernel using the mdadm utility. It is inexpensive, flexible, and performs very well on modern CPUs.
- Hardware RAID: Uses a dedicated physical controller card with its own processor to manage the drives. This offloads work from the system CPU.
- Firmware RAID ("FakeRAID"): Uses motherboard BIOS/UEFI features mixed with minimal OS drivers.

### Common RAID Levels

- **RAID 0** (`Striping`): Splits data evenly across disks. Offers high speed, but no redundancy (if one disk fails, all data is lost). Requires at least 2 disks.
- **RAID 1** (`Mirroring`): Copies identical data to two or more disks. Provides high reliability and safety, but costs more storage space. Requires at least 2 disks.
- **RAID 5** (`Distributed Parity`): Spreads data and parity information across all member disks. Can survive the loss of one disk. Requires at least 3 disks.
- **RAID 10** (`Striping + Mirroring`): Combines mirroring and striping. Offers high performance and high redundancy, requiring at least 4 disks.
