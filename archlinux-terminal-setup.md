# Archlinux 终端设置

### 改变终端颜色

    $ git clone git://github.com/sigurdga/gnome-terminal-colors-solarized.git
    $ cd gnome-terminal-colors-solarized
    $ ./solarizels
    $ ./install.sh

### 安装zsh

    $ yaourt -S zsh
    $ git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
    $ cp ~/.zshrc ~/.zshrc.orig
    $ cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
    $ chsh -s /usr/bin/zsh
    $ echo vi='vim' >> ~/.zshrc
    $ echo ls='ls --color=auto' >> ~/.zshrc

### 改变ls配色

    $ git clone git://github.com/seebi/dircolors-solarized.git
    $ cp ~/dircolors-solarized/dircolors.256dark ~/.dircolors.256dark
    $ echo eval 'dircolors ~/.dircolors.256dark' >> ~/.zshrc

### 改变vim配色

    $ git clone git://github.com/altercation/vim-colors-solarized
    $ cd vim-colors-solarized/colors
    $ mkdir ~/.vim/color
    $ cp solarized.vim ~/.vim/color

修改~/.vimrc，修改colorscheme参数为

`colorscheme solarized`

###安装vim插件

    $ git clone https://github.com/wklken/k-vim
    $ cd k-vim
    $ sh -x install.sh

如果遇到youcompleteme无法安装，则先手动安装clang，并使用--system-libclang调用系统库

    $ yaourt -S clang
    $ ./install.sh --clang-completer --system-libclang





