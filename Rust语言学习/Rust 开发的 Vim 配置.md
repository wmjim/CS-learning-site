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

### 安装 vim-plug

1. 使用 curl 命令下载 vim-plug 源码：

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

2. 使用 vim-plug 的目录结构规划如下，之后安装的插件将存放在 plugged 目录中：
![[images/926715f30605d2bf8d87765baf6d1c03_MD5.jpeg]]

3. 在 `~/.vimrc` 配置文件中增加 plug-vim 部分：

```.vimrc
call plug#begin('~/.vim/plugged')
" plug list

call plug#end()
```
