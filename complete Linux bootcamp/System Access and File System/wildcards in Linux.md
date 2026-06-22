
## wildcards in Linux

Wildcards in Linux (also known as globbing) are special symbols used by the shell to match patterns of file and directory names. When you execute a command with a wildcard, the shell automatically expands the pattern into a list of matching file paths before executing the command. This allows you to perform operations like listing, moving, or deleting hundreds of files instantly with a single command.

### wildcards

#### 1. `*` :
  - Matches zero or more characters.
  - Example Pattern: `*.txt`
  - Matches: `file.txt, notes.txt, .txt`

#### 2. `?` :
  - Matches exactly one character.
  - Example Pattern: `file?.log`
  - Matches: `file1.log, fileA.log`

#### 3. `[ ]` : 
  - Matches one character from a defined set or range.
  - Example Pattern: `image[1-3].png`
  - Matches: `image1.png, image2.png, image3.png`

#### 4. `[! ]` : 
  - Matches one character not in the defined set.
  - Example Pattern: `file[!0-9].txt`
  - Matches: `fileA.txt (but not file1.txt)`


### Expanded Syntax & Techniques

#### 1. Range Matches [...] : You can define explicit sets or alphanumeric ranges inside square brackets to tighten your criteria:
  - `[aeiou]` matches any single lowercase vowel.
  - `[a-z]` matches any single lowercase letter.
  - `[A-Z]` matches any single uppercase letter.
  - `[0-9]` matches any single numeric digit.

#### 2. Brace Expansion {...} : 

Brace expansion is technically not a traditional wildcard because it generates arbitrary strings rather than checking matching files on the disk, but it behaves similarly in everyday usage.

  - `touch file{A,B,C}.txt` creates `fileA.txt`, `fileB.txt`, and `fileC.txt` simultaneously.
  - `mkdir dir{1..3}` creates directories named `dir1`, `dir2`, and `dir3`.














