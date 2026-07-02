
## grep/egrep text processing command

The grep (Global Regular Expression Print) command in Linux is a foundational text-processing utility used to search files or standard input for lines matching a specified pattern. The egrep utility is a shortcut for grep -E, which enables Extended Regular Expressions (ERE) to support complex regex syntax without needing backslash escapes.

`egrep` is generally used as Logical OR (`|`), eg. `grep -E "error|warning|critical" /var/log/nginx/error.log`

### syntax: 

- `grep [OPTIONS] "PATTERN" [FILE...]`
- `egrep [OPTIONS] "PATTERN" [FILE...]`

### `grep` options:

- `-i` : Ignores text letter-casing (case-insensitive matching).
- `-v` : Inverts the search to output lines that do not match the pattern.
- `-n` : Displays the matching line numbers alongside the text.
- `-c` : Counts and prints only the total number of matching lines.
- `-r` : Recursively searches all files inside a directory and its subdirectories.
- `-w` : Matches the exact whole word only, preventing partial matches within larger words.
- `-o` : Prints only the exact matching text segment instead of the entire line.
