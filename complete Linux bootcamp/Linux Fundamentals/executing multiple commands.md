
## executing multiple commands

To execute multiple commands in Linux on a single line, use a command separator or conditional operator like ;, &&, or ||.

Each operator behaves differently depending on whether the previous command succeeded or failed.

### 1. Unconditional Execution (`;`)

The semicolon (;) runs commands sequentially one after another, regardless of whether the previous command succeeds or fails. eg. `mkdir my_folder; cd my_folder; pwd`

### 2. Conditional Success Execution (`&&`)

The logical AND operator (&&) runs the next command only if the preceding command completes successfully (returns an exit status of 0). eg. `cd my_folder && rm -rf *`

### 3. Conditional Failure Execution (`||`)

The logical OR operator (||) runs the next command only if the preceding command fails (returns a non-zero exit status). eg. `mkdir new_dir || echo "Directory creation failed!"`

### 4. Parallel Execution (`&`)

The ampersand (&) pushes the preceding command to the background, allowing the next command to start running immediately at the same time. eg. `sleep 10 & echo "This prints while sleeping"`



