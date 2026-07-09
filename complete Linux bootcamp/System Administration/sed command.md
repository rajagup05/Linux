
## sed command in linux

The sed command (short for stream editor) in Linux is a non-interactive command-line utility used to parse, filter, and transform text dynamically. It processes text line-by-line, making it exceptionally fast for automated scripts, searching, find-and-replace tasks, and file formatting without needing to open the file in a traditional editor.

syntax: `sed [options] 'command' file_name`

### examples

- Finding and Replacing Text (Substitution): `sed 's/apple/mango/' fruit.txt` (The s flag dictates a text substitution operation.)
- Replace all occurrences globally across the file: `sed 's/apple/mango/g' fruit.txt` (Append the global /g modifier flag to catch multiple occurrences per line.)
- Replace only the Nth occurrence on a line: `sed 's/apple/mango/2' fruit.txt`
- Delete a specific line number (e.g., line 5): `sed '5d' data.log`
- Delete a range of lines (e.g., lines 3 through 7): `sed '3,7d' data.log`
- Delete lines matching a specific keyword or pattern: `sed '/error/d' system.log`
- Delete all completely blank rows: `sed '/^$/d' input.txt`
