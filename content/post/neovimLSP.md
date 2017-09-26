+++
date = "2017-04-19T12:33:39+02:00"
description = "How add Dart completion to Neovim"
meta_img = "/images/image.jpg"
tags = ["dart", "neovim", "LSP"]
title = "Dart Completion in Neovim using Language Server Protocol"
+++

In this short and simple tutorial we will add Dart completion to Neovim using
[Language Server Protocol](http://langserver.org/).

First of all I will suppose that you already have install [Neovim](https://github.com/neovim/neovim/wiki/Installing-Neovim) and [Dart](https://www.dartlang.org/install) in your machine.

## List of programs that we will need:

- [dart_language_server](https://github.com/natebosch/dart_language_server)
- [LanguageClient-neovim](https://github.com/autozimu/LanguageClient-neovim) (Neovim Plugin)
- [nvim-completion-manager](https://github.com/roxma/nvim-completion-manager) (Neovim Plugin)

## Step 1. Install dart_language_server

Since we already have Dart installed, we can install dart_language_server with this command:

``` dart
pub global activate dart_language_server
```

Add the **.pub-cache/bin** in your path (.bashrc or .zshrc file) so the server can be run as **dart_language_server**.
Example:

``` bash
export PATH="$PATH":/home/<your-user-name>/.pub-cache/bin
```

## Step 2. Install LanguageClient-neovim

You can use any plugin manager available in neovim in this case we will use [vim-plug](https://github.com/junegunn/vim-plug).

``` vim
Plug 'autozimu/LanguageClient-neovim', { 'do': ':UpdateRemotePlugins' }
```

Add this configuration to your **init.vim**:

``` vim
" Required for operations modifying multiple buffers like rename.
set hidden

let g:LanguageClient_serverCommands = {
    \ 'dart': ['dart_language_server'],
    \ }
```
## Step 3. Install nvim-completion-manager

Again we are using vim-plug to install this plugin.

``` vim
Plug 'roxma/nvim-completion-manager'
```

## Step 4. Have fun
Open a dart file in neovim. Activate LanguageClient-neovim with this command:

``` vim
:LanguageClientStart
```
![image](../../img/neovimLSP.png)

You will notice that **dart_language_server** also gives us error checking, jump to definition functionalities.
