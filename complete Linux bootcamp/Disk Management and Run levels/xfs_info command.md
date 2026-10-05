
## `xfs_info` command

The xfs_info command in Linux is a utility used to display the geometry and feature details of an existing XFS filesystem. It helps system administrators inspect parameters like block sizes, allocation groups, and log settings.

Technically, xfs_info acts as a front-end script equivalent to running the filesystem expansion tool xfs_growfs with the -n (no change/print geometry) flag.

### Syntax

```
xfs_info [options] [mount-point | block-device | file-image]
```

- `mount-point`: The directory path where the XFS filesystem is currently mounted (e.g., `/mnt/data`).
- `block-device`: The raw partition file (e.g., `/dev/sdb1`).
