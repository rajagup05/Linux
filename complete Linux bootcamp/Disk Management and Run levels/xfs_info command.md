
## `xfs_info` command

The xfs_info command in Linux is a utility used to display the geometry and feature details of an existing XFS filesystem. It helps system administrators inspect parameters like block sizes, allocation groups, and log settings.

Technically, xfs_info acts as a front-end script equivalent to running the filesystem expansion tool xfs_growfs with the -n (no change/print geometry) flag.

### Syntax

```
xfs_info [options] [mount-point | block-device | file-image]
```

- `mount-point`: The directory path where the XFS filesystem is currently mounted (e.g., `/mnt/data`).
- `block-device`: The raw partition file (e.g., `/dev/sdb1`).

### Anatomy of `xfs_info` Output

When you run xfs_info /mnt/data, you will receive a structured block of metadata text. Here is a breakdown of what the primary fields mean:

    meta-data=/dev/sdb1              isize=512    agcount=4, agsize=262144 blks
             =                       sectsz=512   attr=2, projid32bit=1
             =                       crc=1        finobt=1, spinodes=0, rmapbt=0
             =                       reflink=1, bigtime=1, inobtcount=1
    data     =                       bsize=4096   blocks=1048576, imaxpct=25
             =                       sunit=0      swidth=0 blks
    naming   =version 2              bsize=4096   ascii-ci=0, ftype=1
    log      =internal log           bsize=4096   blocks=2560, version=2
             =                       sectsz=512   sunit=0 blks, lazy-count=1
    realtime =none                   extsz=4096   blocks=0, rtextents=0


#### 1. meta-data Section

- `isize`: The size of an individual inode in bytes (typically 256 or 512).
- `agcount`: The number of Allocation Groups (AG). XFS divides filesystems into AGs to manage space and allow parallel indexing/allocation operations.
- `agsize`: The size of each Allocation Group, measured in blocks.
- `crc` & `reflink`: Feature bits. crc=1 indicates metadata checksums are enabled for corruption protection. reflink=1 indicates support for copy-on-write file clones.

#### 2. data Section

- `bsize`: The fundamental block size of the filesystem (usually 4096 bytes or 4KiB).
- `blocks`: The total number of data blocks available in the entire filesystem.
- • `sunit` / `swidth`: RAID stripe unit and width values. Ifconfigured during mkfs.xfs, these optimize data alignment across a hardware RAID array.

#### 3. naming Section






