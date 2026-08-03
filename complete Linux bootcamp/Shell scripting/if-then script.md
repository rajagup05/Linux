
## if-then script

In Linux, the if-then statement allows a shell script to perform different actions based on whether a specific condition evaluates to true or false.

### syntax

Every if statement must end with fi (which is "if" spelled backward) to close the block. Keep in mind that spaces inside the brackets [ ] are mandatory; omitting them causes syntax errors.

```
if [ condition ]; then
    # Commands run if condition is true
fi
```

### examples

#### 1. Checking If a File Exists

This script evaluates if a specific file exists on the system before trying to interact with it.

```
#!/bin/bash

if [ -f "/etc/passwd" ]; then
    echo "The file exists."
fi
```

#### 2. Number Comparisons (If-Then-Else)

When comparing integers, Linux uses structural flags rather than standard symbols like < or >.

- `-eq` (Equal to)
- `-ne` (Not equal to)
- `-gt` (Greater than)
- `-lt` (Less than)
