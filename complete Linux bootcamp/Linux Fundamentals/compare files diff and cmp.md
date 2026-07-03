
## compare files diff and cmp

The primary difference is that diff compares files line by line to show all detailed textual discrepancies, whereas cmp compares files byte by byte and stops at the very first difference it encounters. Because of this, diff is ideal for analyzing source code or text files, while cmp is the superior choice for checking if binary files are identical.

### diff

The diff command tells you how to change one file to match another. It scans through text, tracking what lines were added, modified, or deleted. It is heavily used in software development to generate code patches.

- Basic Output: Uses symbols like `<` (lines unique to File 1), `>` (lines unique to File 2), and change hints like `c` (change), `a` (add), or `d` (delete).
- Unified Format (`diff -u file1 file2`): Generates a standard git-style patch view showing surrounding text with `-` and `+` markers.
- Side-by-Side (`diff -y file1 file2`): Renders both files right next to each other in the terminal for visual skimming.

### cmp

The cmp command answers a simpler question: Are these two files completely identical? If it finds a single mismatch, it prints exactly where the disruption happened and aborts further checking.

- First Mismatch Only: If `file1` has "Hello" and `file2` has "Hella", `cmp` will report a difference at byte 5, line 1, and close immediately.
- Silent Mode (`cmp -s file1 file2`): Suppresses all printed text. It only leaves behind a bash exit status ($?): `0` if identical, or `1` if different. This is ideal for automated scripting pipelines.
- Verbose Mode (`cmp -l file1 file2`): For deeper investigation, this forces cmp to continue scanning and list every single differing byte along with its offset value.
