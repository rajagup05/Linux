
## how to combine split files

In Linux, you can split large files into smaller pieces using the split command and recombine them later using the cat command. This process works flawlessly for both plain text and binary files (like archives, videos, or ISOs).

### 1. Splitting Files

The split command breaks a target file into chunks. By default, it generates pieces containing 1,000 lines each, naming them xaa, xab, xac, and so on.

- Split by File Size: `split -b 100M large_video.mp4`
- Split by Line Count: `split -l 5000 server.log`
- Add a Custom Prefix: `split -b 50M archive.tar.gz chunk_` (Creates files: chunk_aa, chunk_ab, chunk_ac...)
- Use Numeric Suffixes: `split -b 10M -d data.bin fragment_` (Creates files: fragment_00, fragment_01, fragment_02...)


### 2. Combining Files

To reconstruct your original file, use the cat (concatenate) command alongside an output redirector (>). Linux matches the wildcards alphabetically, which aligns perfectly with how split labels files.

- Rejoin Alphabetical Chunks: `cat x* > restored_file.mp4`
- Rejoin Custom Prefix Chunks: `cat chunk_* > restored_archive.tar.gz`
- Direct Unzipping Without Saving Chunks: `cat chunk_* | tar -xvz`
