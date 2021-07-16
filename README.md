# oh my zsh+item最全配置教程
作为一名计算机专业的学生，学会使用Terminal是一件必备技能，而一款好看的终端界面，将大大提高生产效率。网上的配置资料零碎，基于自己的配置经验，决定写一份教程，以供参考，因为笔者已经装好环境，为了更好的安装体验，文中一些图片参考网上，将在文末注明出处。由于笔者使用的是Mac，因此介绍的是Mac上的一款终端替代软件[`item2`](https://iterm2.com/),并将使用`oh my zsh`对其进行配置，也将会介绍一些插件的使用，话不多说，先看效果图。
[![WMkHyD.md.png](https://z3.ax1x.com/2021/07/16/WMkHyD.md.png)](https://imgtu.com/i/WMkHyD)

这里放上我的[GitHub仓库](https://github.com/command-z-z/oh-my-zsh-item2)，文件自取，欢迎`star🌟`。

## 准备工作
### 1. 安装item2
直接进入[item2官网](https://iterm2.com/),点击download，根据提示一步步下载即可。

### 2. homebrew安装
[Homebrew](https://brew.sh/)是Mac上的包管理工具，功能强大具体以后专门写篇博客讲解。
如果你没有安装Homebrew，可以复制以下代码，在终端中执行安装。
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
`

### 3.git的安装
我们已经安装了homebrew，因此可以使用brew来快速安装git，复制一下代码:
`brew install git`

### 4.oh my zsh安装
由于Mac默认使用的是Bash，相比于默认的Bash，Zsh有更多的自定义选项，并支持扩展。因此 Zsh可以实现更强大的命令补全，命令高亮等一系列酷炫功能,可以使用以下代码进行切换;
`chsh -s /bin/zsh`
如果想要切换回可以使用以下代码:
`chsh -s /bin/bash`
换到`zsh`之后就可以使用以下代码进行安装:
`sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"`
这里放下[oh my zsh](https://github.com/ohmyzsh/ohmyzsh)的github仓库
到此zsh的安装基本结束了，效果如下，为了达到更酷炫的效果，我们还需要一些插件进行配置。
[![WMuZb8.md.png](https://z3.ax1x.com/2021/07/16/WMuZb8.md.png)](https://imgtu.com/i/WMuZb8)

## 主题安装
### 5.安装字体
1. 使用以下代码安装PowerLine
`pip3 install powerline-status --user`
2. 安装PowerFonts，将以下代码一条条放入终端，`//`后为注释不用复制。
```sh
mkdir ~/Desktop/OpenSource  //首先在桌面上创建一个文件夹

cd ~/Desktop/OpenSource  //进入此文件夹

git clone https://github.com/powerline/fonts.git --depth=1  //克隆源码

cd fonts  //进入fonts文件夹

./install.sh //安装
```
安装好字体库之后，我们来设置iTerm2的字体，具体的操作是iTerm2 -> Preferences（可以使用快捷键`command`+`,`） -> Profiles -> Text，在Font区域选中Change Font，然后找到Meslo LG字体。有L、M、S可选，看个人喜好：
[![WMlSsI.md.png](https://z3.ax1x.com/2021/07/16/WMlSsI.md.png)](https://imgtu.com/i/WMlSsI)
### 6.安装背景配色
1. 安装Solarized，代码如下：
```sh
cd ~/Desktop/OpenSource

git clone https://github.com/altercation/solarized

cd solarized/iterm2-colors-solarized/

open .
```
在打开的finder窗口中，双击Solarized Dark.itermcolors和Solarized Light.itermcolors即可安装明暗两种配色：
[![WMlIfg.md.png](https://z3.ax1x.com/2021/07/16/WMlIfg.md.png)](https://imgtu.com/i/WMlIfg)
再次进入iTerm2 -> Preferences -> Profiles -> Colors -> Color Presets中根据个人喜好选择这两种配色中的一种即可：
[![WM1djs.md.png](https://z3.ax1x.com/2021/07/16/WM1djs.md.png)](https://imgtu.com/i/WM1djs)
### 7.安装主题
主题的安装网上有很多教程，也有很多主题选择，可以查看github上的[各种主题](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)，如果你和笔者一样不知道选择哪一个主题,可以选择`random`主题，它会在每次打开`item2`时切换一个主题，具体操作如下，输入以下代码:
`vi ~/.zshrc`
[![WM4dBj.md.png](https://z3.ax1x.com/2021/07/16/WM4dBj.md.png)](https://imgtu.com/i/WM4dBj)
在红线中修改主题为`random`，vim的使用简要说明，用上下左右键移动光标到要修改处，按键盘`a`进入insert模式，即可修改，修改完成按`esc`键退出，然后用键盘输入`:wq`即保存文件，其他操作可参考[vim资料](https://command-z-z.github.io/2020/10/08/Terminal-%E6%93%8D%E4%BD%9C%E6%8C%87%E4%BB%A4%E9%9B%86%E5%90%88/)。

输入以下代码，让文件生效：
`source ~/.zshrc`

### 8. 背景修改
具体操作iTerm2 -> Preferences（可以使用快捷键`command`+`,`） -> Profiles -> Window，在红线处点击选择本地的一张图片作为背景。
[![WMThQK.md.png](https://z3.ax1x.com/2021/07/16/WMThQK.md.png)](https://imgtu.com/i/WMThQK)
在此页面你也可以修改上图中的Transparency和Blur修改背景的透明度以及模糊度，还可以修改其他参数，定制出属于你的美化终端。

## 快捷操作
为了方便大家提取，我已将我的4个文件背景配置输出为json文件，放在我的[github仓库](https://github.com/command-z-z/oh-my-zsh-item2)中,4张背景图也放置在仓库中有需要自取，具体操作为克隆仓库，然后按下图指示导入json文件即可，记得下载相应背景图。
[![WMHJCn.md.png](https://z3.ax1x.com/2021/07/16/WMHJCn.md.png)](https://imgtu.com/i/WMHJCn)

## 插件安装
zsh中内置了丰富的插件，可在官网上查看[Wiki](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins)，选择合适的插件，这里讲解几种我自己常用的插件，有待挖掘：

首先输入：`vi ~/.zshrc`，可以查看插件安装，在此输入插件名即可,有些上面已经装了就不再叙述。
[![WMOTw8.md.png](https://z3.ax1x.com/2021/07/16/WMOTw8.md.png)](https://imgtu.com/i/WMOTw8)

#### 1. git（内置）

作用：可以使用各种`git`命令缩写。
比如:
```bash
git add --all ===> gaa

git commit -m ===> gcmsg
```
查看所有 git 命令缩写
`cat ~/.oh-my-zsh/plugins/git/git.plugin.zsh`

#### 2. z（内置）

作用：目录间快速跳转,不用再一直`cd`了
输入`z`查看可以跳转路径。
`z -x 无效路径`可以删除路径。

#### 3.git-open
作用：在终端里打开当前项目的远程仓库地址

不要小看这个插件欧，每次改完本地代码，当你想用浏览器访问远程仓库的时候，就知道这个插件多方便了

**安装**
克隆项目
`git clone https://github.com/paulirish/git-open.git $ZSH_CUSTOM/plugins/git-open`

在 ~/.zshrc 中配置
`plugins=(其他的插件 git-open)`

使配置生效:
`source ~/.zshrc`

#### 4. sudo(内置)
作用:当有时输入语句权限不够时，可按两下`esc`自动补全sudo。




# 参考
[1.iTerm2 + Oh My Zsh 打造舒适终端体验](https://www.jianshu.com/p/9c3439cc3bdb)
[2.zsh oh-my-zsh 插件推荐](https://hufangyun.com/2017/zsh-plugin/)