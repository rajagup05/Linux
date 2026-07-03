
## sort/uniq text processors command

The sort and uniq commands in Linux are powerful text-processing tools used to arrange, clean, and deduplicate data from text files or standard streams. While sort reorders data alphabetically or numerically, uniq detects and filters duplicate text—but it only catches adjacent (consecutive) duplicate lines. Because of this behavior, the two tools are almost always chained together in a pipeline (sort file.txt | uniq) to ensure comprehensive text deduplication.

### The `sort` Command

By default, sort rearranges the lines of a text file alphabetically and outputs the result directly to your terminal.

- `-n`: Sorts lines numerically. Without this, numbers are treated as strings (e.g., 10 will sort before 2).
- `-r`: Reverses the order of the sort output (descending order).
- `-f`: Standardizes the comparison by ignoring letter case (case-insensitive sorting).
- `-k`: Sorts by a specific column or "key" index rather than the start of the line.
- `-u`: Bypasses the need for a pipeline by sorting and removing duplicate lines in a single pass.

examples: 

- Sort a file alphabetically (A to Z): `sort names.txt`

- Sort a file numerically in descending order: `sort -nr numbers.txt`

Sort a CSV file based on the data in the second column: `sort -t',' -k2 data.csv`



### The `uniq` Command

The uniq command filters out duplicate lines from your data stream. However, if the matching lines are separated by different data, uniq will miss them. You must route data through sort first.

- `-c`: Prefixes each output line with the exact count of how many times it appeared.
- `-d`: Only prints the duplicate lines, ignoring any line that only appears once.
- `-u`: Only prints completely unique lines that have no matches anywhere else in the file.
- `-i`: Compares the lines case-insensitively.


examples: 

- Safely remove all duplicates across the entire file: `sort lines.txt | uniq`
- Identify only the lines that contain duplicate entries: `sort lines.txt | uniq -d`
- Show only lines that appear exactly once in the stream: `sort lines.txt | uniq -u`

