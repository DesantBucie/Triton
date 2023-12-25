
# Triton

## Words of introduction

Only tested on macOS for now.

Unlike normal Vim, this follows XDG(if you don't have XDG variables set, defaults will be assigned) which means:

* .vim is in ~/.local/share/vim/ etc.

**and possibly**

* vimrc is in ~/.config/vim/vimrc

To make this work add this line to your .profile(or .bash\_profile, .zsh\_profile etc.) to have .vimrc in .config/vim/vimrc:

 `export VIMINIT='let $MYVIMRC="$HOME/.config/vim/vimrc" | source $MYVIMRC'`

***YOU CAN IGNORE THIS and vimrc will stay in `~`,  but .vim will be in `~/.local/share/vim`***

## Instalation

You have to have git installed and in PATH.

Clone repository.

Run install.sh.

Then delete repository.

## LSP

This supports LSP via lsp plugin from [yegappan](https://github.com/yegappan/lsp). You have a template how do add LSP server in vimrc.

Remember that vimrc uses vim9script, so his README examples won't work, [**read doc/lsp.txt instead.**](https://github.com/yegappan/lsp/blob/main/doc/lsp.txt) Also servers not mentioned in docs should work, you can use nvim-lspconfig for help. And don't forget about installing [LSP server](https://microsoft.github.io/language-server-protocol/implementors/servers/). 

## Plugin management

TODO: package groups 

* `:Packinstall <url>` - for downloading the plugin. It will automatically be loaded. If you want manual control: [^1]
* `:Packupdate` - update all plugins. **Any changes will be reverted**(git reset --hard).
* `:Packlist` - list all plugins installed.
* `:Packdelete <name>` - removes plugin.
* `:Packunload <name>` - unloads plugin(but keeps it on drive)
* `:Packload <name>` - loads plugin back in

## Keybindings

The leader key can be different depending on system. For me it's `\`. You can customise it in _**vimrc**_ (`var mapleader = 'key'`).

* \<leader> + n - tree explorer
* \<leader> + t - new tab
* \<leader> + s - vertical split
* \<Ctrl> + w - switch splits
* \<Tab> - When completion window is visible, goes down in completion list
* \<Shift-Tab> - When completion window is visible goes up in completion list
* :Template - load template if avaliable.

## Advices

* Bind ESC to Caps-Lock, for example on mac:

![Esc](https://raw.github.com/DesantBucie/DesantBucie/master/easy.nvim/esc.gif)

## Removing Triton

Delete .vimrc and ~/.local/share/vim/pack/triton


[^1]: then you'll need to put plugin to ~/.local/share/vim/pack/triton/opt/<pluginname> and
load it under some circumstances with packadd. More on that you'll find on stack overflow. I assume 99% of times you won't care.
