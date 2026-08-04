
## for loops 

In Linux, a for loop is a fundamental control flow statement used in Bash scripting and the command line to automate repetitive tasks by iterating over a list of items, such as numbers, strings, files, or command outputs.

### syntax

The most common structure of a standard Bash for loop looks like this:

```
for variable in list
do
    command1
    command2
done
```

Alternatively, you can write a for loop as a single-line command directly in your terminal:

```
for variable in list; do command1; command2; done
```

### examples: 

- Loop Through a List: Loops through explicit items like strings, numbers, or variable arrays.

```
for item in apple banana cherry
do
    echo "Fruit: $item"
done
```

- Loop Through a Number Range: Uses brace expansion {`start..end..step`} to generate a sequence.

```
for i in {1..5}
do
    echo "Number: $i"
done
```
