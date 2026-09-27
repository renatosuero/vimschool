+++
title = "Buffers"
date =  2017-10-30T10:39:33-04:00
weight = 10
+++

# Buffers

A buffer is Vim's in-memory representation of a file. You can have multiple buffers open at the same time, even when only one file is visible on screen. Buffers are one of the most useful ways to work efficiently with many files without constantly reopening and closing them.

## Opening files in buffers

When you open a file in Vim, it is loaded into a buffer:

```vim
:e myfile.txt
```

This opens `myfile.txt` as a buffer. You can also open additional files in separate buffers:

```vim
:edit file1.txt
:edit file2.txt
```

Each buffer can hold a different file or document.

## Listing buffers

See the list of open buffers:

```vim
:ls
```

This shows each buffer with its number, status, file name, and whether it is active or hidden.

## Switching buffers

Move to the next buffer:

```vim
:bn
```

Move to the previous buffer:

```vim
:bp
```

Jump directly to a buffer by number:

```vim
:buffer 3
```

Or the shortened version:

```vim
:b3
```

## Creating and editing buffers

Open a new empty buffer:

```vim
:enew
```

Open a file in a new buffer:

```vim
:edit newfile.txt
```

Save the current buffer:

```vim
:w
```

Save all modified buffers:

```vim
:wall
```

Close the current buffer and keep Vim open:

```vim
:bd
```

Close the current buffer even if it is modified and you have not saved it:

```vim
:bd!
```

## Hidden buffers

When you switch away from a modified buffer, Vim may keep it open in the background. This is called a hidden buffer. Hidden buffers remain loaded even when you are not editing them.

You can switch buffers without losing changes:

```vim
:bn
```

If you try to quit Vim while hidden buffers are modified, Vim warns you before exiting.

## Buffer status indicators

In `:ls`, Vim uses letters to indicate buffer state:

| Indicator | Meaning |
| --- | --- |
| `h` | Hidden buffer |
| `%` | Current buffer |
| `a` | Active buffer |
| `+` | Modified buffer |
| `=` | No changes |

This helps you see which files are open, which one you're editing, and which ones still need to be saved.

## Buffer navigation tips

Use the buffer list to keep several files close at hand without closing them. Common workflows include:

- Open several project files in buffers
- Jump between them with `:bn` and `:bp`
- Save all files with `:wall`
- Close files you are done with with `:bd`

## Using the argument list

Another common workflow is to open a list of files and then step through them. Example:

```vim
:args file1.txt file2.txt file3.txt
```

Then:

```vim
:next
:prev
```

This is useful when you want to work through a specific list of files instead of every open buffer.

## Try it

1. Open two or three files in buffers.
2. Run `:ls` to see them listed.
3. Move between them with `:bn` and `:bp`.
4. Edit the content of one file, switch away, and come back.
5. Verify the buffer still exists and your changes are kept.
6. Save with `:w` or save all with `:wall`.
7. Remove one with `:bd` when you're finished.

Buffers are the basic way Vim keeps track of open files. Understanding them makes multi-file editing much easier and more efficient.
