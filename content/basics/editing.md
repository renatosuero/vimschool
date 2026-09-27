+++
title = "Editing"
date =  2017-10-30T10:09:39-04:00
weight = 8
+++

# Editing Text

Editing is at the heart of using Vim. Once you understand how to navigate and enter insert mode, you'll spend most of your time performing edits: changing text, adding lines, deleting content, and rearranging text.

## Basic editing in insert mode

To start editing, enter insert mode from Normal mode with one of these keys:

```vim
i    " Insert before cursor
a    " Append after cursor
I    " Insert at beginning of line
A    " Append at end of line
o    " Open a new line below
O    " Open a new line above
```

Once in Insert mode, type normally. Your text will be inserted at the cursor position.

To return to Normal mode and save your changes, press `Esc`.

## Replacing text

Replace a single character with `r`:

```vim
r<char>
```

For example, `rx` replaces the character under the cursor with `x`.

To replace an entire word, use `cw` (change word):

```vim
cw
```

This deletes the word and enters insert mode so you can type the replacement.

## Deleting text

Delete a single character with `x`:

```vim
x     " Delete char under cursor
X     " Delete char before cursor
```

Delete an entire word with `dw`:

```vim
dw
```

Delete to the end of the line:

```vim
D
```

Delete an entire line:

```vim
dd
```

## Undoing and redoing changes

Undo the last change:

```vim
u
```

Redo the change you just undid:

```vim
<Ctrl-r>
```

Undo the last N changes:

```vim
Nu
```

For example, `5u` undoes the last 5 changes.

## Joining and splitting lines

Join two lines together:

```vim
J
```

This merges the current line with the next line, removing the line break.

Split a line at the cursor by going to the position and pressing:

```vim
<Ctrl-o>  " In insert mode, or from normal mode: Enter Insert mode at the cursor
```

Then press `Esc` to exit insert mode and the split is complete.

## Repeating edits

Repeat the last change with `.` (dot):

```vim
.
```

This is incredibly useful when you've performed an edit and want to apply the same change elsewhere.

## Working with multiple lines

Edit multiple lines at once by selecting them in visual mode, then performing an operation:

```vim
V         " Visual line mode
j         " Select down
d         " Delete selected lines
```

Or change text on multiple lines:

```vim
V         " Visual line mode
jj        " Select multiple lines
c         " Change selected text
```

## Try it

1. Open a test file and enter insert mode with `i`.
2. Type some text and press `Esc` to return to Normal mode.
3. Delete a character with `x` or a word with `dw`.
4. Undo the change with `u` and redo with `<Ctrl-r>`.
5. Replace a character with `r`.
6. Join two lines with `J`.
7. Practice using `.` to repeat changes.

Editing efficiently in Vim comes from combining simple commands and repeating them. The more you practice, the faster you'll become.
