
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

### examples

- `awk '{print $1, $3}' data.txt`: Print the first and third columns of a whitespace-delimited file
- `awk -F, '{print $1, $2}' inventory.csv`: Use the -F flag to parse standard comma-separated values (CSV)
- `awk '/ERROR/ {print $0}' system.log`: Print all lines that contain the keyword "ERROR" (acts like grep)
- `awk '$3 > 100 {print $1, $2}' sales.txt`: Print lines where the third column contains a number greater than 100
- `awk '{print NR, $0}' document.txt`: Prepend the line number to every line of a document
- `awk '{sum += $1} END {print "Total:", sum}' numbers.txt`: Sum all the values in the first column and print the grand total at the end
