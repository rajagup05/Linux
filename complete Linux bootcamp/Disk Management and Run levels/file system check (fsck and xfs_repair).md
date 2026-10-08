
## file system check (fsck and xfs_repair)

In Linux, fsck and xfs_repair are essential system utilities used to check and maintain file system consistency, fix structural corruption, and prevent data loss.

The fundamental difference lies in their architecture: fsck is a generic wrapper tool designed primarily for the Ext family of file systems (Ext2/3/4), while xfs_repair is a dedicated utility exclusively engineered for the XFS file system architecture.

Before using either tool, always unmount the file system you intend to check. Running a file system check or repair on a live, mounted file system can severely damage and permanently corrupt your data.

`sudo umount /dev/sdXN`

