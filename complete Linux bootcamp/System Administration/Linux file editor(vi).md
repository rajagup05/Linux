
## Linux file editor(vi)

The vi editor is the default command-line text editor pre-installed on almost all Linux and Unix-like operating systems. It is a modal editor, meaning the keyboard keys perform different functions depending on the current operational mode you are in. On modern Linux distributions, typing vi usually opens its advanced version, Vim (Vi IMproved).

### The Three Modes of vi

- Command Mode: The default mode when the editor opens. Every keystroke is interpreted as a command (e.g., navigating, copying, deleting). You cannot type text in this mode.
- Insert Mode: The mode used to write and edit text. You switch to this mode from Command Mode by pressing i.
- Last Line / Ex Mode: The mode used for system tasks like saving, quitting, or running terminal commands. It is accessed by typing a colon (:) from Command Mode.

### essential commands

- Opening a File: `vi filename.txt`
- `i`: Switch to Insert Mode to type text before the cursor.
- `Esc`: Return to Command Mode from any other mode.

**Cursor Navigation (In Command Mode**):

- `h`: Move left.
- `j`: Move down.
- `k`: Move up.
- `l`: Move right.
- `0 (zero)`: Jump to the start of the current line.
- `$`: Jump to the end of the current line.
- `G`: Jump to the last line of the file.
- `:number`: Jump directly to a specific line number (e.g., :10)

**Editing & Deleting (In Command Mode)**

Key commands for editing text include `x` (delete character), `dd` (delete line), and `p` (paste), along with `u` for undoing actions.











