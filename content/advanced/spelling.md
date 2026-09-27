+++
title = "Check Spelling"
date =  2017-10-30T10:40:05-04:00
weight = 13
+++

# Check Spelling

Vim includes built-in spell checking for text files. This is useful when writing documentation, notes, or prose in natural language. It can help catch mistakes and highlight words that may be misspelled.

## Enabling spell checking

Turn spelling on with:

```vim
:set spell
```

You can also specify a language:

```vim
:set spelllang=en_us
```

Common languages include:

- `en_us`
- `en_gb`
- `es`
- `fr`

To turn spelling off:

```vim
:set nospell
```

## Moving through misspelled words

When spell checking is enabled, Vim highlights incorrectly spelled words. Move to the next misspelling with:

```vim
]s
```

Move to the previous misspelling with:

```vim
[s
```

## Fixing misspelled words

When the cursor is on a misspelled word, you can suggest replacements:

```vim
z=
```

This opens a list of suggestions and lets you choose a replacement.

You can also add a word to your personal dictionary:

```vim
zg
```

This marks the current word as good and adds it to your personal spell file.

To mark a word as bad or ignore it for the current session:

```vim
zw
```

This adds the word to the list of words to ignore.

## Ignoring or marking words

Sometimes you may want to ignore a word repeatedly. Use:

```vim
zg
```

for a good word, and:

```vim
zw
```

for a word to ignore.

## Spell-checking settings

Check the current spell settings:

```vim
:set spell?
```

Set the spell language:

```vim
:set spelllang=en_us
```

You can also set spell checking for only selected buffers or based on file type. For example, many plugins and syntax files will enable spelling automatically in Markdown files.

## Try it

1. Open a text file and enable spell checking with `:set spell`.
2. Use `]s` and `[s` to move between errors.
3. Press `z=` to correct a misspelled word.
4. Use `zg` to add a word to your personal dictionary.
5. Try changing the language with `:set spelllang=en_us`.

Spell checking is especially useful for writing documentation, commit messages, and notes without leaving Vim.
