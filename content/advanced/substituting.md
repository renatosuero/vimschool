+++
title = "Substituting Text"
date =  2017-10-30T10:39:05-04:00
weight = 9
+++

# Substituting Text

The substitution command lets you replace text inside Vim. It is one of the most common and useful commands for editing files efficiently, especially when you want to update repetitive patterns.

## Basic substitution

Use the `:s` command to replace text on the current line:

```vim
:s/old/new/
```

This replaces the first occurrence of `old` on the current line with `new`.

To replace all occurrences on the current line, add the `g` flag:

```vim
:s/old/new/g
```

## Substitute across the whole file

Use `%` to apply the substitution to the entire file:

```vim
:%s/old/new/g
```

This replaces every occurrence of `old` with `new` throughout the buffer.

## Confirming replacements

Add the `c` flag to confirm each replacement interactively:

```vim
:%s/old/new/gc
```

Vim asks for each match before making the change.

## Replacing only on specific lines

You can restrict substitution to a range of lines. For example, replace in lines 10 through 20:

```vim
:10,20s/old/new/g
```

Or replace only in the current line:

```vim
:.,+5s/old/new/g
```

## Case-insensitive substitution

Use `i` to make substitutions case-insensitive:

```vim
:%s/old/new/gi
```

This matches `old`, `Old`, `OLD`, and similar variations.

## Using regular expressions in substitutions

Substitution commands support regular expressions too. For example:

```vim
:%s/\d\+/NUMBER/g
```

This replaces every number with `NUMBER`.

For example, change `foo123` to `foo456` only when a number is present:

```vim
:%s/foo\d\+/foo456/g
```

## Using replacement groups

You can reference previous matches with `\1`, `\2`, and so on. Example:

```vim
:s/\(foo\)\(bar\)/\2\1/
```

This swaps the order of `foo` and `bar` in the matched text.

## Deleting text with substitution

To delete a pattern, replace it with an empty string:

```vim
:%s/old//g
```

This removes all occurrences of `old` from the file.

## Quick examples

Change `TODO` to `DONE` everywhere:

```vim
:%s/TODO/DONE/g
```

Remove trailing spaces:

```vim
:%s/\s\+$//g
```

Replace every double space with a single space:

```vim
:%s/  / /g
```

## Try it

1. Open a file with repeated words or patterns.
2. Try `:s/old/new/` on one line.
3. Use `:%s/old/new/g` to replace everywhere.
4. Test a regex pattern, such as `:%s/\d\+/NUMBER/g`.
5. Use `:%s/old/new/gc` to confirm each replacement.

Substitution is one of Vim's most efficient editing tools, especially when you need to make the same change across many lines quickly.
