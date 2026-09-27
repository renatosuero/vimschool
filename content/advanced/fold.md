+++
title = "Fold"
date =  2017-10-30T10:36:57-04:00
weight = 5
+++

# Folding

Folding allows you to collapse sections of code or text, keeping the overall structure visible while hiding details. This is especially useful for navigating large files and focusing on specific sections.

## Creating folds manually

In Normal mode, select the lines you want to fold using Visual mode:

```vim
V
```

Then create a fold with:

```vim
zf
```

For example, to fold from the current line to line 20:

```vim
:20fold
```

Or visually select lines and press `zf` to fold the selection.

## Automatic folding methods

Vim can automatically create folds based on different criteria. Set the `foldmethod` option:

```vim
:set foldmethod=indent
```

Common fold methods:

| Method | Description |
| --- | --- |
| `manual` | Create folds manually with `zf` (default) |
| `indent` | Folds based on indentation level |
| `expr` | Folds based on an expression |
| `syntax` | Folds based on language syntax |
| `diff` | Folds unchanged lines in diff mode |
| `marker` | Folds based on text markers like `{{{` and `}}}` |

For example, in Python files with indentation-based folding:

```vim
:set foldmethod=indent
```

## Opening and closing folds

Once folds are created, navigate and toggle them:

| Command | Action |
| --- | --- |
| `zo` | Open fold at cursor |
| `zc` | Close fold at cursor |
| `za` | Toggle fold at cursor |
| `zO` | Open all folds recursively |
| `zC` | Close all folds recursively |
| `zA` | Toggle all folds recursively |
| `zR` | Open all folds (reduce) |
| `zM` | Close all folds (maximum) |

For example, to toggle the fold under the cursor:

```vim
za
```

## Fold level and depth

Control how deep folding goes:

```vim
:set foldlevel=0
```

The `foldlevel` determines which folds are open by default:

- `foldlevel=0`: All folds closed
- `foldlevel=1`: Only top-level folds open
- `foldlevel=2`: Two levels of nesting open

Increase the fold level to see more detail:

```vim
zL
```

Decrease it to hide more detail:

```vim
zl
```

## Viewing fold status

Check the current fold configuration:

```vim
:set foldmethod?
:set foldlevel?
```

To display line numbers and fold columns together:

```vim
:set number
:set foldcolumn=3
```

The fold column on the left shows fold status with `+` for closed folds and `-` for open folds.

## Deleting folds

Remove folds without affecting the text:

```vim
zd
```

Delete all folds in the buffer:

```vim
zD
```

Eliminate the fold structure entirely:

```vim
:set foldmethod=manual
```

## Practical fold markers

Use markers for portable, explicit fold control:

```vim
:set foldmethod=marker
```

Then add markers in your file:

```python
# Function one {{{
def function_one():
    pass
# }}}

# Function two {{{
def function_two():
    pass
# }}}
```

The `{{{` and `}}}` mark fold boundaries. Customize the markers:

```vim
:set foldmarker=<!--,-->
```

## Try it

1. Open a file with multiple functions or sections.
2. Set `foldmethod=indent` to enable automatic folding.
3. Use `zR` to open all folds and see the entire file.
4. Use `zM` to close all folds and see only the structure.
5. Navigate with `zj` (next fold) and `zk` (previous fold).
6. Use `za` to toggle individual folds open and closed.
7. Adjust `foldlevel` to control the default visibility.

Folds are powerful for maintaining focus on relevant code sections while keeping the overall file structure visible.
