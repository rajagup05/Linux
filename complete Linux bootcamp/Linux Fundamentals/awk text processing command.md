
## awk text processing command

The Linux awk command is a highly versatile, stream-oriented data extraction and text processing language. It reads input line by line, automatically splits each line into fields (columns) based on a whitespace delimiter, and runs specified programmatic actions on those fields. It is exceptionally useful for log parsing, data transformations, and report generation.

### syntax: 

`awk [options] 'pattern { action }' input_file`

- `options`: Modifiers like `-F` to define a custom field delimiter (e.g., `-F`, for CSV files).
- `pattern`: A condition or regular expression filter; awk only executes the action if the line meets this criterion.
- `{ action }`: The actual command blocks to execute on matching records, enclosed in curly braces

### Built-in Essential Variables

- `$0`: References the entire current line.
- `$1, $2, ... $N`: Reference specific fields (columns) within the line.
- `NF`: Number of Fields (the total column count for the current line).
- `$NF`: Returns the text string of the very last column in the line.
- `NR`: Number of Records (the absolute line number currently being processed).
