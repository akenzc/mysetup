# Mac设置

## 软件安装

### homebrew 安装

先在appstore里安装xcode，再安装homebrew。
	
	$ ruby -e “$( -fsSL https://raw.github.com/mxcl/homebrew/go)"


### cask 安装
	$ brew tap phinze/homebrew-cask && brew install brew-cask

### 常用软件安装

	$ brew cask install qq
	$ brew cask install evernote
	$ brew cask install google-chrome
	$ brew cask install dropbox
	$ brew cask install goagentx
	$ brew cask install firefox
	$ brew cask install Skype
	$ brew cask install keepassx 
	$ brew cask install mou
	$ brew cask install the-unarchiver
	$ brew cask install xunlei
	$ brew cask install alfred
	$ brew cask install iterm2
	$ brew cask install skitch
	$ brew cask install istat-menus
	$ brew cask install middleclick
	
### 其他软件安装

暂无

---------------------------------

## 终端配置

终端选用iTerm2，使用`zsh`，首先要修改配色，需要给3个工具配色，`terminal`、`vim` 和 `ls`。

### zsh 安装

	$ brew install zsh
	$ git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
	$ cp ~/.zshrc ~/.zshrc.orig
	$ cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
	$ chsh -s /bin/zsh

### terminal配色
首先下载 Solarized：
	
	$ git clone git://github.com/altercation/solarized.git

导入`solarized/iterm2-colors-solarized`中的配置，选用`Solarized Dark.itermcolors`配置。

### ls配色

Mac底层是基于freeBSD的，所以常用工具例如`ls` 、`grep`也都是freeBSD版本的，所以我们需要安装`coreutils`来使用GNU的`ls`。

	$ brew install coreutils
	
装完需要根据提示进行设置，在`.profile`和`.zshrc`文件中加入

	export PATH="/usr/local/opt/coreutils/libexec/gnubin:$PATH"
	export MANPATH="/usr/local/opt/coreutils/libexec/gnuman:$MANPATH"

设置完后重新打开终端，运行命令`man ls`来查看是否是GNU的文档，如果是，则安装成功。

`ls`同样也使用solarized配色，安装dircolors-solarized

	$ git clone git@github.com:seebi/dircolors-solarized.git
	$ cp dircolors-solarized/dircolors.256dark ~/.dircolors.256dark
	$ echo 'eval `dircolors .dircolors.256dark`' >> ~/.zshrc


### MacVIM安装

	$ brew install macvim
	
vim的配置暂时使用k-vim的配置。

	$ git clone https://github.com/wklken/k-vim.git
	
先安装一些依赖：

	$ brew install ctags
	$ sudo pip install pyflakes
	$ sudo pip install pylint
	$ sudo pip install pep8
	
安装插件

	$ cd k-vim/
	$ sh -x install.sh
	
修改`.zshrc`，增加：

	alias vi='mvim -v'
	alias vim='mvim -v'
	
----------------------------

## Python 环境安装

先安装一些依赖
	
	$ brew install readline sqlite gdbm pkg-config

再安装python

	$ brew install python
	
最后修改`.zshrc`

	$ export PATH=/usr/local/bin/python:$PATH
	
安装ipython

	$ sudo pip install ipython
