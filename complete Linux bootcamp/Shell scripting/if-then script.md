
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

