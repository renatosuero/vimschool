+++
title = "Marks"
date =  2017-10-30T10:37:23-04:00
weight = 6
+++

# Marks

Marks let you save a location and return to it quickly. They are especially useful when you are editing in two different parts of a long file.

## Setting a mark

In Normal mode, place the cursor at the location you want to remember and type `m` followed by a letter:

```vim
ma
```

This sets mark `a` at the current cursor position. The letter can be any lowercase letter from `a` to `z`.

## Jumping to a mark

Use a backtick followed by the mark name to return to the exact cursor position:

```vim
`a
```

A single quote followed by the mark name jumps to the first non-blank character on the marked line:

```vim
'a
```

For example, use `ma` to mark a function, continue editing elsewhere, and then use `` `a `` to return to the exact position.

Marks can also be used as motion targets for operators. This deletes from the cursor through the line containing mark `a`:

```vim
d'a
```

The backtick form preserves character-level precision when it is used with an operator:

```vim
d`a
```

## Local and file marks

- Lowercase marks (`a`–`z`) are local to the current buffer. The same mark name can refer to different locations in different files.
- Uppercase marks (`A`–`Z`) are file marks. They can be used to jump to a location in another file:

```vim
mA
`A
```

Whether file marks survive after Vim exits depends on Vim's `viminfo` configuration.

## Listing and deleting marks

Use `:marks` to list the marks that are currently available:

```vim
:marks
```

Delete one or more marks with `:delmarks`:

```vim
:delmarks a
:delmarks abc
```

Use `:delmarks!` to delete all user-defined lowercase and uppercase marks.

## Useful automatic marks

Vim maintains several marks automatically:

| Mark | Meaning |
| --- | --- |
| `` `. `` | Position of the last change |
| `` `^ `` | Position where the last insert mode stopped |
| `` `[ `` | Start of the last change or yank |
| `` `] `` | End of the last change or yank |
| `` `< `` | Start of the last Visual selection |
| `` `> `` | End of the last Visual selection |
| `` `. `` | Position of the last change |
|
| `''` | Position before the last jump, at the first non-blank character |
| `` `` `` | Position before the last jump, at the exact cursor position |

The automatic marks are useful for recovering your place after an edit or jump. For example, `` `. `` takes you to the position of the most recent change.

## Try it

1. Put the cursor on an interesting line and type `ma`.
2. Move to another part of the file with `/` or `G`.
3. Return with `` `a `` and compare it with `'a`.
4. Run `:marks` to inspect the saved location.
5. Delete the mark with `:delmarks a`.

Use a few lowercase marks for temporary navigation within a file, and uppercase marks when you need named locations across files.
