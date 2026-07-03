
## sort/uniq text processors command

The sort and uniq commands in Linux are powerful text-processing tools used to arrange, clean, and deduplicate data from text files or standard streams. While sort reorders data alphabetically or numerically, uniq detects and filters duplicate text—but it only catches adjacent (consecutive) duplicate lines. Because of this behavior, the two tools are almost always chained together in a pipeline (sort file.txt | uniq) to ensure comprehensive text deduplication.

### The sort Command

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
