# iota2

> Making Imaginations, Real

<i2.iotasquare@gmail.com>

```
 ██╗ ██████╗ ████████╗ █████╗ ██████╗
 ██║██╔═══██╗╚══██╔══╝██╔══██╗╚════██╗
 ██║██║   ██║   ██║   ███████║ █████╔╝
 ██║██║   ██║   ██║   ██╔══██║██╔═══╝
 ██║╚██████╔╝   ██║   ██║  ██║███████╗
 ╚═╝ ╚═════╝    ╚═╝   ╚═╝  ╚═╝╚══════╝
```

[![BSD licensed](https://img.shields.io/badge/license-GPL3-blue.svg)](https://raw.githubusercontent.com/iota2/dev-setup/master/LICENSE)


# VIM Configuration
Following plugins are required to be installed separately.
Also for some configurations marked files need to be copied to respected path.

## Selected Vundle plugins for VIM
- [x] scrooloose/nerdtreedg
- [x] majutsushi/tagbar
- [x] kien/ctrlp.vim
- [x] bling/vim-airline
- [x] vim-airline/vim-airline-themes
- [x] Lokaltog/powerline
- [x] flazz/vim-colorschemes
- [x] morhetz/gruvbox
- [x] nathanaelkane/vim-indent-guides
- [x] DoxygenToolkit.vim
- [x] tpope/vim-surround
- [x] ntpeters/vim-better-whitespace
- [x] Valloric/YouCompleteMe
- [x] vim-scripts/indentpython.vim
- [x] tmhedberg/SimpylFold
- [x] klen/python-mode
- [x] scrooloose/syntastic

## Configuring Vim Vundle:
__Configuration__     | __Operation__
:----                 | :----
**GET Vundle**        | `git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim`
**UPDATE FROM REPO**  | `~/.vimrc`
**INSTALL FROM VIM**  | `:PluginInstall`

## Install and configure Ctags:
__Configuration__   | __Operation__
:----               | :----
**GET Ctags:**      | `sudo apt-get install ctags`
**CREATE TAGS:**    | `ctags -R`
**INFO:**           | Tags can be accessed through Tagber extention
**TAGBAR USAGE:**   | <kbd>F8</kbd> or `:TagbarToggle` on vim

## Compile and Install YCM
__Configuration__   | __Operation__
:----               | :----
**GET CLANG:**      | `sudo apt-get install cmake clang`
**GO TO YMC:**      | `cd ~/.vim/bundle/YouCompleteMe`
**INSTALL YMC:**    | `python3 install.py --clangd-completer`

## Configured Shortcuts
__Plugin__    |   __Configured Shortcuts__
:----         | :----
**nerdTree**  | <kbd>"</kbd>
**Ctrlp**     | [<kbd>ctrl</kbd> + <kbd>p</kbd>]
**Tagbar**    | <kbd>F8</kbd> or `:TagbarToggle`
**Doxygen**   | `:Dox` [Cursor should be on Function Name]

# License
> `GNU GPU v3` <br>
> This program is free software; you can redistribute it and/or
> modify it under the terms of the GNU General Public License
> as published by the Free Software Foundation; either version 3
> of the License, or (at your option) any later version.
> This program is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
> GNU General Public License for more details.

**Free Software, Hell Yeah!**

