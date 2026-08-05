
## case statements

In Linux shell scripting (Bash), a case statement is a control flow structure used to match a single value against multiple patterns. It functions as a cleaner, more readable alternative to complex, deeply nested if-elif-else blocks when evaluating a single variable.

syntax: 

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
