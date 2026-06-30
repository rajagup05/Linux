
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

### 3. `more`

An older, legacy alternative to less. It operates similarly but lacks advanced backward navigation.

- Standard usage: `more filename.txt`
- Navigation: Press `Spacebar` to go down a full page, or `Enter` to advance line-by-line.


### 4. `head`

The head command lets you inspect the starting lines of a document.

- Standard usage: `head filename.txt` (Outputs the first 10 lines).
- Custom line count: `head -n 20 filename.txt` (Outputs the first 20 lines).

### 5. tail

The tail command displays the closing lines of a text file. It is widely used by system administrators to troubleshoot background services.

- Standard usage: `tail filename.txt` (Outputs the last 10 lines).
- Custom line count: `tail -n 5 filename.txt` (Outputs the last 5 lines).
- Live view flag: `tail -f application.log` (Keep the file open and stream new additions in real-time). Use `Ctrl + C` to stop monitoring.
