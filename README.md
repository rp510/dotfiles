# ~josh

These are my dotfiles. There are many like them, but these are mine.

## intro

Dotfiles are used to personalize a *NIX system. I use these dotfiles on Linux and Mac OS X systems.

I use the excellent `zsh` for my shell, but most of the aliases, shell functions, etc in `.zshrc` and elsewhere should work just fine in `bash`.

There are comments throughout my dotfiles attributing all known original sources.

## install

* `git clone git://github.com/joshdick/dotfiles.git ~/.dotfiles`
* `cd ~/.dotfiles`
* `./install.sh`

The install script looks for all files and directories in the root of the repository ending in the .symlink extension. It then symlinks those files and directories into your home directory with a dot prepended and the .symlink extension removed.

Your existing dotfiles *should* be safe since the script will not symlink over any existing dotfiles with the same name (you should see warnings from `ln`). Seeing warnings from `ln` means that some subset of the dotfiles will have been symlinked in, so [re]move the conflicting files and re-run the script to ensure all dotfiles are symlinked in correctly.

I take no responsibility for any havoc the install script may wreak on your system...it works for me!

## usage

`~/.localrc` will be sourced if it exists. Anything that should be kept secret/doesn't need to be version controlled should go in this file. It is useful for machine-specific configuration.

`~/.bin` contains git submodules for various utilities I use. These are added to `PATH` as appropriate via the `~/.bin/bin_init.zsh` script.

`~/.vim` contains [vundle][1] as a git submodule, which manages the vim plugins I use.

  [1]: https://github.com/gmarik/vundle