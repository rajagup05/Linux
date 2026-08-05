
## do-while  loops

In Linux shell scripting (Bash), there is no native do-while loop keyword, but you can easily emulate one by using a standard while loop with a true condition and a conditional break at the end. This ensures that the code block always executes at least once before checking the condition.

Here is the standard structural template for a do-while loop in Linux:

```
#!/bin/bash

# Initialize variables
count=1

do_while_loop() {
    while true; do
        # 1. RUN CODE (Executes at least once)
        echo "Loop execution number: $count"
        
        # Increment counter
        ((count++))

        # 2. CHECK CONDITION (Exit if condition is met)
        if [ $count -gt 5 ]; then
            break
        fi
    done
}

do_while_loop
```

```
#!/bin/bash

while true; do
    # Prompt the user
    read -p "Enter a number greater than 10: " num

    # Validate the condition at the end
    if [ "$num" -gt 10 ]; then
        echo "Thank you! You entered $num."
        break  # Exit the loop since condition is satisfied
    else
        echo "Invalid input. Try again."
    fi
done
```

A classic use case for a do-while loop is prompting a user for input and forcing the prompt to appear at least once.

```
#!/bin/bash

while true; do
    # Prompt the user
    read -p "Enter a number greater than 10: " num

    # Validate the condition at the end
    if [ "$num" -gt 10 ]; then
        echo "Thank you! You entered $num."
        break  # Exit the loop since condition is satisfied
    else
        echo "Invalid input. Try again."
    fi
done
```
