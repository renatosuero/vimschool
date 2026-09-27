+++
title = "Pathogen"
date =  2017-10-30T10:56:27-04:00
weight = 5
+++

# Pathogen

Pathogen is a simple and elegant plugin manager for Vim. It allows you to organize your plugins in separate directories, making it easy to install, update, and remove plugins without cluttering your `.vim` directory.

## Why Pathogen?

Without a plugin manager, all plugin files go into the same directories, making it hard to manage multiple plugins. Pathogen solves this by loading plugins from separate bundle directories.

## Installing Pathogen

First, create the necessary directories:

```bash
mkdir -p ~/.vim/autoload ~/.vim/bundle
```

Then download Pathogen:

```bash
curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim
```

On Windows, create `%USERPROFILE%\_vim\autoload\` and `%USERPROFILE%\_vim\bundle\`.

## Configuring Pathogen in .vimrc

Add these lines to your `.vimrc`:

```vim
execute pathogen#infect()
syntax on
filetype plugin indent on
```

This line must appear before any syntax highlighting or filetype settings.

## Installing plugins with Pathogen

To install a plugin, clone it into the bundle directory:

```bash
cd ~/.vim/bundle
git clone https://github.com/user/plugin-name.git
```

For example, to install NERDTree:

```bash
git clone https://github.com/preservim/nerdtree.git ~/.vim/bundle/nerdtree
```

Pathogen will automatically load the plugin the next time you start Vim.

## Updating plugins with Pathogen

To update a plugin, use git pull inside its directory:

```bash
cd ~/.vim/bundle/plugin-name
git pull
```

You can update all plugins at once:

```bash
for plugin in ~/.vim/bundle/*; do
  if [ -d "$plugin/.git" ]; then
    cd "$plugin"
    git pull
  fi
done
```

## Removing plugins with Pathogen

To remove a plugin, simply delete its directory:

```bash
rm -rf ~/.vim/bundle/plugin-name
```

Pathogen will stop loading it the next time you start Vim.

## Listing installed plugins

See all your installed plugins:

```bash
ls ~/.vim/bundle
```

Or from within Vim:

```vim
:scriptnames
```

## Troubleshooting Pathogen

If a plugin isn't loading:

1. Check that it's in `~/.vim/bundle/`
2. Verify the pathogen#infect() line is in your `.vimrc`
3. Restart Vim and check for error messages
4. Run `:scriptnames` to see what plugins are loaded

## Example workflow

```bash
# Install Pathogen
mkdir -p ~/.vim/autoload ~/.vim/bundle
curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim

# Install a plugin (e.g., vim-sensible)
git clone https://github.com/tpope/vim-sensible.git ~/.vim/bundle/vim-sensible

# Update the plugin
cd ~/.vim/bundle/vim-sensible
git pull

# Remove the plugin
rm -rf ~/.vim/bundle/vim-sensible
```

## Try it

1. Install Pathogen following the steps above
2. Add the pathogen#infect() line to your `.vimrc`
3. Restart Vim
4. Install a simple plugin like vim-sensible
5. Verify it loaded with `:scriptnames`
6. Practice updating and removing it

Pathogen is lightweight and straightforward, making it an excellent choice for managing Vim plugins. Once you master it, adding plugins to your workflow becomes effortless.
