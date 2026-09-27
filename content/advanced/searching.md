+++
title = "Searching"
date =  2017-10-30T10:38:49-04:00
weight = 7
+++

# Searching

Vim's search feature helps you find text quickly inside the current file. Searching is one of the most useful commands in Vim because it lets you jump directly to relevant lines without manually scanning the whole file.

## Starting a search

To search forward for a word or pattern, type `/` followed by the text:

```vim
/function
```

This searches the file from the cursor downward. Press `n` to move to the next match and `N` to move to the previous match.

To search backward, use `?` instead:

```vim
?function
```

## Searching for whole words

Use a word boundary to avoid matching partial words:

```vim
/\<function\>
```

This finds only the word `function`, not text like `myfunction`.

## Searching with regular expressions

Vim supports regular expressions in searches. For example:

```vim
/\d\d\d\d
```

matches a four-digit sequence. Pattern matching is extremely useful for finding code patterns quickly.

A few common regex examples:

```vim
/\w\+\s\+\=
```

```vim
/\v\d+
```

Use `:help pattern` for more details about Vim regex syntax.

## Repeating searches

Press `n` to repeat the last search forward and `N` to repeat it backward.

You can also repeat the last search without retyping it by just pressing `/` and then Enter.

## Search options

Vim can be configured to make searches more useful:

```vim
:set ignorecase
```

This makes search matches case-insensitive. To make it case-sensitive again:

```vim
:set noignorecase
```

For smart case matching:

```vim
:set smartcase
```

This means searches are case-insensitive unless the pattern contains uppercase characters.

## Highlighting matches

To temporarily highlight all search results:

```vim
:set hlsearch
```

To disable the highlighting:

```vim
:set nohlsearch
```

You can also clear the current highlight immediately:

```vim
:nohlsearch
```

## Searching across the file

Common movement while searching:

- `n`: next match
- `N`: previous match
- `*`: search for the word under the cursor
- `#`: search backward for the word under the cursor

Example:

```vim
* 
```

This finds the next occurrence of the word currently under the cursor.

## Searching for a pattern in multiple files

Use `:vimgrep` to search across multiple files from within Vim:

```vim
:vimgrep /pattern/ *.py
```

Then jump through the results:

```vim
:cnext
:cprev
```

You can also list all results with:

```vim
:clist
```

## Quick search tips

- Use `*` and `#` to search for the word under the cursor.
- Use `/` and `?` for forward and backward searches.
- Use `n` and `N` to navigate matches.
- Use `:set hlsearch` for easy visual scanning.
- Add `` or other regex tokens when searching for structured patterns.

## Try it

1. Open a file and type `/function`.
2. Press `n` repeatedly to move to the next match.
3. Press `N` to move backwards.
4. Search for the word under the cursor using `*`.
5. Turn on `hlsearch` and then use `:nohlsearch` to clear the highlight.
6. Try a regex such as `/\d\d\d\d`.

Searching is a fundamental Vim skill that helps you move around large files efficiently and find exactly what you need.
