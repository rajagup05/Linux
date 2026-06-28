

## Inputs and Outputs redirect

Input and output redirection in Linux is a powerful built-in shell feature that lets you alter where a command reads its data from and where it sends its results. By default, commands accept input from your keyboard and print their regular output and error messages to your terminal screen. Redirection symbols override these defaults by routing data to or from files, devices, or other commands.

### The three standard streams

Every process run in Linux automatically opens three data channels, known as standard streams:

- **Standard Input (STDIN / File Descriptor 0)**: Handles incoming data, defaulting to the keyboard.
- **Standard Output (STDOUT / File Descriptor 1)**: Handles regular program output, defaulting to the terminal screen.
- **Standard Error (STDERR / File Descriptor 2)**: Handles error messages separately from standard data, defaulting to the terminal screen.

### Output redirection (`>` and `>>`)

Output redirection intercepts data meant for the terminal screen and saves it into a file instead.

- **Overwrite** (`>`): Overwrites the file completely if it already exists or creates a new one if it does not. eg. `echo "Hello World" > output.txt`
- **Append** (`>>`): Adds the output to the bottom of the file without erasing its existing content. eg. `echo "Adding a new line" >> output.txt`
