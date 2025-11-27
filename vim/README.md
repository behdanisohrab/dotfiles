# My vim config

this is my vimrc that i use daily.

## installation

put the vimrc file into your home dir as .vimrc then run:

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

cp vimrc ~/.vimrc
vim +PlugInstall +qall
```

install language servers:

```vim
:CocInstall coc-clangd coc-rust-analyzer coc-pyright coc-sh
```

deps:
```bash
pacman -S clang rust-analyzer python-lsp-server shellcheck ripgrep fzf ctags
```

## mappings

**navigation**
```
ctrl+hjkl    splits
ctrl+n       nerdtree
ctrl+p       fzf files
leader+f     ripgrep
leader+b     buffers
f8           tagbar
f12          ctags
```

**lsp**
```
tab          next completion
shift+tab    prev completion
enter        accept
ctrl+space   trigger
gd           definition
gr           references
gi           implementation
K            docs
leader+rn    rename
```

**build**
```
f5           make/cargo build/zig build
f6           make clean/cargo test
f7           cargo run/zig run
```

**edit**
```
gcc          toggle comment
space        clear search
f2           paste mode
leader+w     save
leader+q     quit
leader+rw    strip whitespace
```

**git**
```
leader+gb    blame line
```

## code style

| lang   | tabs  | width |
|--------|-------|-------|
| c      | tabs  | 8     |
| rust   | space | 4     |
| zig    | space | 4     |
| python | space | 4     |
| bash   | space | 2     |

80 char limit highlighted for kernel work.

## theme

catppuccin macchiato. terminal needs true color support.

## features

- lsp completion for c/cpp/rust/python/bash
- auto format on save (rust/python)
- kernel checkpatch integration (`:CheckPatch`)
- git diff in gutter
- auto header guards for .h files
- auto shebang for .sh files
- linting via ale

## debug

```vim
:CocInfo
:CocCommand rust-analyzer.reload
:CocCommand clangd.restart
:PlugUpdate
```

leader is `\` by default. override:
```vim
let mapleader = ","
```
