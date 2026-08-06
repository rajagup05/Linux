
## case statements

In Linux shell scripting (Bash), a case statement is a control flow structure used to match a single value against multiple patterns. It functions as a cleaner, more readable alternative to complex, deeply nested if-elif-else blocks when evaluating a single variable.

### syntax: 

```
case $variable in
    pattern1)
        # Commands if variable matches pattern1
        ;;
    pattern2|pattern3)
        # Commands if variable matches pattern2 or pattern3
        ;;
    *)
        # Default commands if no other pattern matches
        ;;
# The statement ends with "case" spelled backwards
esac
```

- `case $variable in`: Starts the block and specifies the variable to test.
- `)`: Closes each individual pattern option.
- `|`: Acts as an OR operator to join multiple patterns together.
- `;;`: Terminates the command block for a specific pattern (similar to a break statement).
- `*)`: Acts as the wildcard/default case if no previous patterns match.
- `esac`: Closes the entire conditional block.

### example

```
#!/bin/bash
echo "Enter a fruit (apple, banana, or orange):"
read fruit

case $fruit in
    "apple")
        echo "Apples are red or green."
        ;;
    "banana"|"plantain")
        echo "Bananas are yellow."
        ;;
    "orange")
        echo "Oranges are orange."
        ;;
    *)
        echo "Unknown fruit."
        ;;
esac
```
