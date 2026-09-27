+++
title = "Regular Expressions Review"
date =  2017-10-30T10:39:24-04:00
weight = 8
+++

# Regular Expressions Review

A regular expression, or regex, is a pattern used to match text. Vim uses regexes in searches, substitutions, and many powerful editing commands. Learning the basics will make your searches and replacements much more flexible.

## Basic matching

To search for a literal string, type it directly:

```vim
/hello
```

This finds the word `hello`.

To search for a pattern, use regex syntax. For example, to match any digit:

```vim
/\d
```

The `\d` pattern matches a single digit. To match a sequence of one or more digits:

```vim
/\d\+
```

The `\+` means "one or more".

## Common regex tokens

These are some of the most useful regex patterns in Vim:

| Pattern | Meaning |
| --- | --- |
| `.` | Any single character |
| `*` | Zero or more of the previous atom |
| `\+` | One or more of the previous atom |
| `\?` | Zero or one of the previous atom |
| `\{m,n\}` | Between `m` and `n` repeats |
| `\w` | Word character |
| `\W` | Non-word character |
| `\s` | Whitespace |
| `\S` | Non-whitespace |
| `\d` | Digit |
| `\D` | Non-digit |
| `^` | Start of a line |
| `$` | End of a line |
| `\(` and `\)` | Grouping |
| `\|` | Alternation (or) |

For example:

```vim
/\w\+\s\+\w\+
```

This matches a word followed by whitespace and another word.

## Character classes

Character classes match one of several characters:

```vim
/[A-Z]/
```

This matches any uppercase letter from `A` to `Z`.

```vim
/[0-9a-f]/
```

This matches a single digit or a lowercase hexadecimal character.

## Escaping special characters

Some characters are special in regex syntax and must be escaped when you mean to match them literally:

```vim
/\.
```

This matches a period, because `.` normally means "any character".

```vim
/\+
```

This matches a literal plus sign.

Use a backslash to escape regex metacharacters.

## Anchors

Anchors match a position rather than a character:

```vim
/^Hello/
```

This matches `Hello` at the beginning of a line.

```vim
/World$/
```

This matches `World` at the end of a line.

## Alternation

Use `\|` to match one of several patterns:

```vim
/foo\|bar
```

This matches either `foo` or `bar`.

## Using regexes in substitutions

Regex patterns are especially useful in substitution commands:

```vim
:%s/old/new/g
```

This replaces all occurrences of `old` with `new` in the file.

You can also use groups to rearrange text:

```vim
:%s/\(foo\)\(bar\)/\2\1/g
```

This swaps the order of `foo` and `bar`.

## Practical examples

Match a date in `YYYY-MM-DD` format:

```vim
/\d\d\d\d-\d\d-\d\d
```

Match an email-like string:

```vim
/\w\+@\w\+\.\w\+
```

Match a whole word with boundaries:

```vim
/\<function\>
```

## Try it

1. Search for a pattern like `/\d\+` in a file.
2. Try a word-boundary search with `/\<word\>`.
3. Search for a range of letters such as `/[A-Z]\+`.
4. Use a substitution such as `:%s/old/new/g`.
5. Try an alternation like `/foo\|bar`.

Regular expressions are one of Vim's most powerful features. Once you understand the basic patterns, you can search and edit text with surprising speed and precision.
