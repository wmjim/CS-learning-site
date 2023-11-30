#rust
## Vim 的安装

首先检查你的系统中是否安装 Vim，如果没有安装的话，则在终端执行如下命令进行安装：

```bash
sudo apt-get install vim
```

## 插件管理器
### 插件管理器的选择

Vim 的插件管理也是有许多种的，而我选择的是 [vim-plug](https://github.com/junegunn/vim-plug) 。

vim-plug 是一款轻量级，且功能强大，且易于使用的插件管理器，对我这种喜欢简单的人自是极其友好的。

![[../images/installer.gif]]

### 安装 vim-plug

**1. 使用 curl 命令下载 vim-plug 源码：**

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

**2. 使用 vim-plug 的目录结构规划如下，之后安装的插件将存放在 plugged 目录中：**
![[images/926715f30605d2bf8d87765baf6d1c03_MD5.jpeg]]

**3. 在 `~/.vimrc` 配置文件中增加 plug-vim 部分：**

```.vimrc
call plug#begin('~/.vim/plugged')
" plug list

call plug#end()
```

在 `call plug#begin('~/.vim/plugged')` 和 `call plug#end()` 之间使用 `Plug` 命令列出插件。

### vim-plug 安装插件的 4 种方式

下面介绍在 `~/.vimrc` 配置文件中安装插件 4 种方式：

**1. 安装在 vim-scripts 仓库插件**

```bash
Plug 'PluginName'
```

`PluginName` 中的 `空格` 使用 `-` 替换。

示例：

```bash
Plug 'L9'
```

执行这个指令的时候，首先检查该插件是否已经下载到本地，如果没有下载，则会使用 git 下载，下载的方式如下：

```bash
git -C ~/.vim/plugged clone --recursive https://github.com/vim-scripts/L9.git
```

- `--recursive`是顺便把子模块的代码也一起下载到`~/.vim/plugged/L9`目录中。

然后才是安装该插件。

> 要注意的是：安装插件不等于下载插件，安装插件是对该插件资源的管理， 你自己下载下来，放到对应的位置，但是你没有配置该指令，就不会安装，它的功能你也就用不了，这就是插件管理器的作用， 插件管理器不仅仅是下载插件代码的。这个要搞清楚。

**2. 安装在 GitHub 仓库种的插件**

如果您要安装的插件在 GitHub 仓库中， 那么，配置的格式如下：

```bash
Plug 'userName/repoName'
```

示例：

```bash
Plug 'tpope/vim-fugitive'
Plug 'Lokaltog/vim-easymotion'
Plug 'rstacruz/sparkup', {'rtp': 'vim/'}
Plug 'tpope/vim-rails.git'
```

执行这个指令的时候，首先检测该插件是否已经下载到本地了，如果没有下载， 就会使用 git 下载，下载的方式如下：

```bash
git -C ~/.vim/plugged clone --recursive https://github.com/tpope/vim-fugitive.git
```

- `--recursive`是顺便把子模块的代码也一起下载到`~/.vim/plugged/vim-fugitive`目录中。

**3. 安装在非 GitHub 仓库，但使用 git 管理的插件**

如果您要安装的插件使用 git 管理的，但是它并不在 GitHub 仓库中， 那么配置的格式如下：

```bash
Plug 'git://...'
```

示例：

```bash
Plug 'git:https://gitee.com/mirrors/youcompleteme.git'
```

执行这个指令的时候，首先检测该插件是否已经下载到本地了，如果没有下载， 就会使用 git 下载，下载的方式如下：

```bash
git -C ~/.vim/plugged clone --recursive https://gitee.com/mirrors/youcompleteme.git
```

- `--recursive`是顺便把子模块的代码也一起下载到`~/.vim/plugged/youcompleteme`目录中。

**4. 安装在本地文件系统中的插件**

如果您要安装的插件在本地的文件系统中，那么配置的格式如下：

```bash
Plug 'file://...'
```

示例：

```bash
Plug 'file:///Users/gmarik/path/to/plugin'
```

### vim-plug 命令使用

vim-plug 提供了下面的命令用来管理插件，在 Vim 

| 命令 | 描述 |
| ---- | ---- |
|      |      |
