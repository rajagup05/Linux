
## wc text processor command

The wc (word count) command in Linux is a text-processing utility used to count lines, words, characters, and bytes in a file or from a data stream.

syntax: `wc [options] [filename]`

### default output

```
wc notes.txt
# Output: 14  52 344 notes.txt
```

- `14` – Number of lines.
- `52` – Number of words.
- `344` – Number of bytes.
- `notes.txt` – The name of the file.

### Flags and examples

- `-l` (`--lines`): Counts only the newline characters (total lines). eg. `wc -l file.txt`
- `-w` (`--words`): Counts only the total number of words. eg. `wc -w file.txt`
- `-m` (`--chars`): Counts the total number of characters (accurate for multi-byte UTF-8 text). eg. `wc -m file.txt`
- `-c` (`--bytes`): Counts the total number of bytes. eg. `wc -c file.txt`
- `-L` (`--max-line-length`): Prints the length (number of characters) of the longest line in the file. eg. `wc -L file.txt`

### with pipes

- Count files in a directory: `ls /var/log | wc -l`
- Count specific occurrences: `grep "ERROR" system.log | wc -l`
- Process multiple files: `wc -w report1.txt report2.txt`
