
## truncate file size (truncate)

In Linux, you can quickly reduce or extend a file's size using the built-in truncate command, which modifies the file contents in-place without deleting the file itself, preserving its original permissions and owner attributes.

### Empting a File Completely (0 Bytes): 

`truncate -s 0 filename.txt`

### Shrinking or Extending to a Specific Size

- Shrink or expand to exactly 100 Megabytes: `truncate -s 100M filename.txt`
- Decrease the current size by 10 Megabytes: `truncate -s -10M filename.txt`
- Increase the current size by 50 Megabytes: `truncate -s +50M filename.txt`
