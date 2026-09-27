+++
title = "Macros"
date =  2017-10-30T10:39:38-04:00
weight = 11
+++

# Macros

A macro is a recorded sequence of commands that Vim can replay. This is useful when you need to repeat a complex editing action many times without manually redoing the same steps each time.

## Recording a macro

Start recording a macro with `q` followed by a register letter:

```vim
qa
```

This starts recording into register `a`. Every command you type is saved until you stop recording.

To stop recording, press `q` again:

```vim
q
```

## Running a macro

Replay the macro with `@` followed by the register name:

```vim
@a
```

Repeat the same macro again:

```vim
@@
```

This is especially useful for repeated edits such as formatting several similar lines or updating repeated patterns.

## Example macro

Suppose you want to add a comment marker at the start of several lines. Start by recording the action:

```vim
qa
I# <Esc>
j
q
```

This records these steps in register `a`:

- `I` enters insert mode at the beginning of the line
- `# ` inserts a comment prefix
- `<Esc>` returns to Normal mode
- `j` moves to the next line

Now replay the macro on the next lines:

```vim
@a
@@
```

This applies the same action to the current line and then repeats it for subsequent lines.

## Macro best practices

- Keep macros short and simple.
- Record only the exact actions you need to repeat.
- Use a descriptive register name such as `a`, `b`, or `m`.
- Break complex tasks into smaller macros if needed.

## Using a macro on a range of lines

You can apply a macro to a range by using Visual mode to select lines and then run the macro once per selected line:

```vim
Vjjj
@a
```

This applies the macro to each selected line.

## Editing the macro text

Macros are stored in Vim registers, which you can inspect and edit. View the contents of register `a`:

```vim
"ap
```

This prints the macro stored in register `a`, and you can then copy or adjust it if needed.

## Try it

1. Open a file with several similar lines.
2. Record a macro with `qa`.
3. Perform a simple edit such as inserting a comment prefix.
4. Stop recording with `q`.
5. Replay it with `@a` and then `@@`.
6. Inspect the stored macro with `"ap`.

Macros are a powerful way to automate repetitive edits and are among Vim's most useful time-saving features.
