+++
title = ".vimrc"
date =  2017-10-30T10:35:42-04:00
weight = 5
+++

# The .vimrc File

The `.vimrc` file is your personal configuration file for Vim. It allows you to customize settings, define mappings, enable plugins, and personalize your Vim environment. This file is read when Vim starts up, and it is one of the easiest ways to make Vim fit your workflow.

## Locating and creating your .vimrc

On Linux and macOS, the `.vimrc` file is typically located in your home directory:

```bash
~/.vimrc
```

On Windows, it may be located at:

```bash
%USERPROFILE%/_vimrc
```

To create a new `.vimrc`, open Vim and type:

```vim
:edit ~/.vimrc
```

Then save the file with `:w`.

## Basic settings

Here are some common settings you might want to add to your `.vimrc`:

```vim
" Enable line numbers
set number

" Enable syntax highlighting
syntax on

" Set tab width
set tabstop=4
set shiftwidth=4

" Enable auto-indentation
set autoindent

" Highlight search results
set hlsearch

" Enable smart case for searching
set smartcase
set ignorecase

" Show matching brackets
set showmatch
```

## Keybindings and mappings

You can create custom keybindings in your `.vimrc`. For example:

```vim
" Map Ctrl-j to move down
map <C-j> j

" Map Ctrl-s to save
map <C-s> :w<CR>

" Map the leader key to the space bar
let mapleader = " "

" Map leader+w to save
map <leader>w :w<CR>
```

Use `noremap` to avoid recursive mappings and make custom bindings more predictable:

```vim
noremap <C-l> l
```

## Autocommands

Autocommands execute commands automatically when certain events occur. For example, enable spell checking for Markdown files:

```vim
autocmd FileType markdown setlocal spell
autocmd FileType markdown setlocal spelllang=en_us
```

## Abbreviations

Create text abbreviations that expand when you press space or Enter:

```vim
iabbrev teh the
iabbrev waht what
```

## Loading plugins

If you use a plugin manager like Pathogen, add plugin loading to your `.vimrc`:

```vim
execute pathogen#infect()
syntax on
filetype plugin indent on
```

## Comments in .vimrc

Use `"` to add comments:

```vim
" This is a comment
set number  " Show line numbers
```

## Tips for organizing your .vimrc

- Start with basic settings
- Group related settings together with comments
- Use comments to explain what each section does
- Keep your file readable and maintainable
- Test settings before adding them permanently

## Example minimal .vimrc

```vim
" Basic settings
set number
set expandtab
set tabstop=4
set shiftwidth=4
set autoindent

" Syntax highlighting
syntax on

" Search settings
set hlsearch
set ignorecase
set smartcase

" Show status bar
set laststatus=2

" Use case insensitive search, except when using capital letters
if has('autocmd')
  autocmd BufNewFile,BufRead *.py setlocal expandtab
endif
```

## Try it

1. Open your `.vimrc` with `:edit ~/.vimrc`
2. Add `set number` to enable line numbers
3. Save and reload Vim to see the changes
4. Add a custom keybinding like `map <C-s> :w<CR>`
5. Test it in a new Vim session

Your `.vimrc` is the foundation of your personalized Vim experience. Start simple and gradually add settings and customizations as you become more comfortable with Vim.
