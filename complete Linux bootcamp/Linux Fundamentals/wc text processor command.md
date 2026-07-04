
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

### Flags

- `-l` (`--lines`): Counts only the newline characters (total lines). eg. `wc -l file.txt`
- `-w` (`--words`): Counts only the total number of words. eg. `wc -w file.txt`
