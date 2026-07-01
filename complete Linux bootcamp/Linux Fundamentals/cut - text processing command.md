
## cut - text processing command

The Linux cut command is a powerful command-line utility used to extract specific sections, columns, or fields from lines of text files or standard input streams. It processes text line-by-line, allowing you to slice data using byte positions, character indexes, or specified delimiter characters.

syntax: `cut [OPTIONS] [FILE...]`

### Main Target Flags

- `-f` : Selects specific fields (columns). This is the most popular mode for structured data like CSVs.
- `-c` : Selects precise character positions.
- `-b` : Selects precise byte positions.

### Specifying Position Ranges

- `N` : Individual position (e.g., `-c 5` targets the fifth character).
- `N,M` : Distinct individual positions (e.g., `-f 1,3` extracts fields 1 and 3).
- `N-M` : A range from position N to M (e.g., `-b 1-10`).
- `N-` : From position N all the way to the end of the text line.
- `-M` : From the very beginning of the line up to position M.

### Modifying and Formatting Flags

- `-d "character"` : Changes the field delimiter character from the default tab to your custom character.

examples: 

- `cut -d ',' -f 2 names.csv` : To parse out a single column from a comma-separated file
- `cut -d ':' -f 1 /etc/passwd` : System configurations like /etc/passwd use colons. Isolate the first column (usernames) like this
- `cut -c 1-5 report.txt` : Extract characters 1 through 5 from a text file, regardless of layout dividers
- `echo "John,Doe,30" | cut -d ',' -f 1,3` : Processing Piped Input Streams
