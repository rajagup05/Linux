
## file display commands

### 1. `cat` (Concatenate)

The cat command dumps the complete content of a file straight onto your terminal screen. Avoid using it for massive files, as it will flood your terminal buffer.

- Standard usage: `cat filename.txt`
- Show line numbers: `cat -n filename.txt`
- Combine files: `cat file1.txt file2.txt > combined.txt`


### 2. `less`

The less command is a powerful terminal pager that opens a dedicated window for file reading. It does not read the entire file into memory before opening, making it extremely fast for huge log files.

- Standard usage: `less system.log`
- Navigation: Use `Spacebar` or `PageDown` to move forward, and `b` or `PageUp` to move backward.
- Searching: Press `/` followed by your keyword to search forward. Press `n` to find the next match.
- Exit: Press `q` to safely close the viewer.
