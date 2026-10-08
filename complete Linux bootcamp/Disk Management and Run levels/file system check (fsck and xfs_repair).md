
## file system check (fsck and xfs_repair)

In Linux, fsck and xfs_repair are essential system utilities used to check and maintain file system consistency, fix structural corruption, and prevent data loss.

The fundamental difference lies in their architecture: fsck is a generic wrapper tool designed primarily for the Ext family of file systems (Ext2/3/4), while xfs_repair is a dedicated utility exclusively engineered for the XFS file system architecture.

Before using either tool, always unmount the file system you intend to check. Running a file system check or repair on a live, mounted file system can severely damage and permanently corrupt your data.

`sudo umount /dev/sdXN`

#### 1. fsck (File System Consistency Checker)

fsck serves as a front-end wrapper. When executed, it identifies the target file system type and automatically dispatches the correct backend tool (such as e2fsck for Ext4). It verifies block bitmaps, inode tables, directory structures, and the superblock.

- **Common Use Cases**: Fixing systems that fail to boot, resolving Input/output error prompts, or dealing with partitions that automatically flip to "Read-only" mode because the kernel detected metadata anomalies.
- `fsck -n /dev/sdXN`: Performs a safe dry-run (read-only) check without making modifications.
- `fsck -y /dev/sdXN`: Automatically answers "yes" to all repair prompts. Excellent for automated scripts or when facing hundreds of minor errors.
