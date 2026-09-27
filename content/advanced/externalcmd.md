+++
title = "Running External Commands"
date =  2017-10-30T10:39:52-04:00
weight = 12
+++

# Running External Commands

Vim can run external commands from inside the editor. This is useful when you want to use shell tools for tasks such as compiling code, formatting text, or searching files outside the current buffer.

## Running one command

Use `:!` followed by the shell command:

```vim
:!ls
```

This runs `ls` in the terminal and shows the output without leaving Vim.

## Running a command and reading output

To capture the output of an external command and place it in the current buffer, use `:read` with a shell command:

```vim
:read !date
```

This inserts the output of `date` into the buffer at the cursor position.

## Sending buffer text to a command

You can also send selected text to an external command. For example:

```vim
:%!sort
```

This sorts the entire buffer through the shell's `sort` command.

A range can be used to limit the effect:

```vim
:1,20!sort
```

This sorts only lines 1 through 20.

## Using shell commands with ranges

Use a Visual selection and pipe the content to an external command:

```vim
:'<,'>!tr 'a-z' 'A-Z'
```

This converts the selected text to uppercase using the `tr` command.

## Running a command from the shell

To return to the shell temporarily, use:

```vim
:sh
```

This opens a shell inside the terminal. Type `exit` when you are done to return to Vim.

## Integrating shell tools in editing workflow

External commands are helpful when the shell has a tool that is more suitable than Vim itself. For example:

- `grep` for quick text searching
- `sort` for reordering text
- `sed` for stream editing
- `awk` for structured text processing
- `git diff` or `git status` for project work

## Practical examples

Run a formatter on a file:

```vim
:!black myfile.py
```

Run a shell command for a quick directory listing:

```vim
:!ls -la
```

Insert the current date:

```vim
:read !date
```

Sort the current file:

```vim
:%!sort
```

## Try it

1. Run `:!ls` to see a shell command output.
2. Insert the current date with `:read !date`.
3. Try `:%!sort` on a small test file.
4. Use a range such as `:1,20!sort` to sort just part of the file.
5. Run `:sh` and exit back to Vim.

External commands make Vim more powerful by combining what the editor does best with the many tools available in the shell.
