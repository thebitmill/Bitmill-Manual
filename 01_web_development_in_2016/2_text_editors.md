# Text Editors

We strongly recommend using either VIM or Atom. For historical reasons
we still cover Sublime Text.

## VIM

## NeoVim

Please consider using [NeoVim](https://neovim.io/).

## Beginning

+ <http://dhruvasagar.com/2012/08/24/vim-in-my-muscle-memory>

## Using help

The documentation in help is usually exemplary.

## Coding Helps

Vimdiff! Learn it!

## Required Plugins

The following is a list which all users of Vim MUST use/learn.

1. Fugitive (Git wrapper / plugin)
2. Syntastic

## Map Leader

It is highly recommended to map your leader to spacebar!

```
let mapleader = "\<Space>"
```

## Next Steps

+ <https://sheerun.net/2014/03/21/how-to-boost-your-vim-productivity/>

## VIM Setup for Web Development

+ <https://github.com/zperrault/vimrc.js>
## Atom

Atom is an open source browser by GitHub built on Node (Electron).

## Sublime Text 2

Previously Sublime Text 2 was our preferred editor after Vim. This has
now changed and we highly recommend using the Atom Editor instead.

## Package Control

Packages in Sublime are most easily controlled with Package Control
<https://packagecontrol.io/>. Initial installs should be done by following the
instructions here: https://packagecontrol.io/installation#2.  Syncing Packages

Detailed information about syncing packages can be found at
<https://packagecontrol.io/docs/syncing>. Basically all you have to do is sync
your .config/sublime-text-2/Packages/User/ folder, and Package Control will
take care of the rest. Remember, you have to install Package Control on all the
computers you use it for. Normally, Package Control is installed following the
step above, but automate this a package file for Package Control can placed in
`.config/sublime-text-2/Installed Packages`. Then sublime installs it
automatically.
