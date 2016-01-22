---
layout: post
title: Atom编辑器入门到精通(一) 安装及使用基础
date: '2015-12-18 16:29'
---

原创时间:2015-12-18<br>更新时间:2016-01-21

## 为什么选择使用Atom
Atom是GitHub推出的一款编辑器,被称为21世纪的黑客编辑器,主要的特点是现代,易用,可定制.
我之前也用过多款编辑器,现总结一下个人对各编辑器的看法:

Vim是我用的时间最长也是折腾时间最长的编辑器<br>优点是逼格高,定制性强,编辑效率高,资源占用少,还可以终端操作<br>缺点是学习曲线陡峭,经常出一些莫名其妙的错误,突然就是一堆调试信息闪过,长得最丑,哪怕是使用了各种插件美化,还是最丑.另外就是自身特性太少,过于依赖插件,如果要实现最基本的IDE的功能,需要装一大堆插件,插件本身的质量和相互之间的兼容性也是个问题

Emacs的优点是功能强大,啥都可以实现,因为他本身就是个操作系统啊,缺点是入门门槛高,我当时为了用Emacs还学了两大本关于Emacs和Lisp的书呢,但是我个人觉得它最大的问题就是快捷键太反人类,特别是在用笔记本时手指真的受不了...

SublimeText:长得很漂亮,至少在它刚出来时算是最漂亮的编辑器了,自带一些编辑器应该有的功能,使得不需要怎么配置就能上手.缺点是闭源,收费,Vim模式的光标太丑,对中文支持不好,都出来几年了Linux下还是连中文都打不出来(虽然可以通过某些方法解决,但一定程度上能说明作者对中国用户的态度,这也是闭源表现出来的一个问题),

VSCode:微软推出的编辑器,前段时间刚开源了,感觉和Atom很像,我很看好这款编辑器,但现在的问题是出来的时间太短,功能和插件不够丰富,生态圈还没有形成,也许再过两年会统治世界呢

Atom跟上面的编辑器比起来优点是比较均衡,上手简单,零门槛,资源占用不高,自身支持的功能就挺多,配置起来也很方便,还有一大堆插件可以选择,还开源免费呢,而且在对中文的支持上也没什么问题.

本教程主要参考Atom的[官方文档](https://atom.io/docs) 1.4.0版,教程中所用的图片很多也取自那里,在后文中就不一一注明了.

## 安装
打开[官方主页](https://atom.io/)
![官方主页](/home/peter/Pictures/linux-downloads.png)
网页会自动判断你的操作系统,给出其对应的下载按钮
比如我的系统是Ubuntu,就可以点击`Download .deb`按钮来下载系统对应的安装包
如果要下载其他系统的安装包,点击`Other platforms`链接即可
### Mac
将下载的zip安装包解压后将解压出的`Atom`应用拖到应用目录下

### Windows
运行安装包安装

### Linux
如果是基于Debian的发行版,执行命令:
```
sudo dpkg -i atom-amd64.deb
```
如果是RedHat,则执行:
```
rpm -i atom.x86_64.rpm
```

安装完成后运行Atom,将会看到这样的界面,说明我们已经安装成功了
![界面](/home/peter/Pictures/first-launch.png)


## 基本使用
### 命令面板
Atom在很多地方学习和参考了以前的优秀的编辑器的功能,命令面板就是其一.
当你第一次看到它时,还以为在用Sublime呢
命令面板是Atom中最常用的功能之一,当你在编辑器中使用快捷键`Ctrl+Shift+P`时,就会看到它
![控制面板](/home/peter/Pictures/command-palette.png)
在控制面板中可以输入Atom中和插件中定义的所有命令,并且支持模糊搜索
比如说当你输入cboo时,所有包含有这4个字符的命令就都列出来了
在列出的命令后还显示了此命令对应的快捷键(如果有的话)

### 设置窗口
Atom使用起来很方便的一点就是自带了可视化的设置窗口,不像传统的编辑器那样需要手动修改配置文件
![设置窗口](/home/peter/Pictures/settings.png)
你可以使用三种方式来打开设置窗口
1. 通过主菜单`Edit`->`Preferences`来打开设置窗口
2. 在命令面板中输入命令`Settings View:Open`来打开,因为命令窗口支持模糊查询,所以只需要输入`svo`,就可以了
3. 使用快捷键`Ctrl+,`

在设置窗口中可以设置和管理各种编辑器行为,键盘快捷键,插件,主题等内容

#### 设置窗口界面主题和代码高亮
Atom自带了4种窗口主题和8种代码高亮方式
可以通过设置窗口中的Themems页面来配置和修改
另外还有n多n多第三方制作的主题可以安装,安装方法在后面会讲到
![主题设置](/home/peter/Pictures/theme.png)

### 文件操作
#### 打开文件
你可以通过主菜单`File`->`Open File`或者快捷键`Ctrl+O`来打开文件选择窗口
![打开文件](/home/peter/Pictures/open-file.png)

#### 保存文件
主菜单 `File`->`Save`
快捷键 `Ctrl+S`
另存为: `Ctrl+Shift+S`
保存所有文件: `Ctrl+Alt+S`

#### 打开文件夹
打开文件夹是一个很实用的功能.比如打开一个项目的根目录,感觉就像是在使用IDE一样
你可以通过在主菜单选择`File`->`Open Folder`来打开一个目录,也可以使用快捷键`Ctrl+Shift+O`
如果你已经打开了一个目录,又想在当前窗口中再打开一个目录,请在主菜单选择`File`->`Add Project Folder`或者使用快捷键`Alt+Ctrl+O`
在打开一个文件夹以后该文件夹下的所有子目录和文件都会以目录树的方式显示在主窗口左边,就像下图一样
![打开文件夹](/home/peter/Pictures/project-view.png)
在目录树栏中还可以对文件进行新建打开,重命名,删除等操作


## 配置
Atom的配置文件位于HOME目录的.atom文件夹下<br>
主要的配置文件有:

`~/.atom/config.cson`

主要的配置文件

`~/.atom/keymap.cson`

快捷键的配置文件

`~/.atom/init.coffee`
每当Atom有新窗口建立时都会调用此文件



# 插件

```

apm install vim-mode

apm install atom-beautify

apm install linter

apm install emmet

apm install file-icons

apm install color-picker

apm install git-plus

apm install project-manager

apm install highlight-line
```


# 快捷键
## 显示列表

```

Ctrl+Shift+P        显示命令列表



Ctrl+T              显示文件列表

Ctrl+B              显示已打开文件列表

Ctrl+Shift+B        显示未同步文件列表



Ctrl+R              显示当前文件符号列表

Ctrl+Shift+R        显示工程内符号列表(需要tags文件)
```

## 搜索

```

Ctrl+F              文件内搜索

Ctrl+Shift+F        工程内搜索
```

## 分栏

```

Ctrl+K 右/下         新建分栏

Ctrl+K Ctrl+右/下    切换分栏焦点

Ctrl+W              关闭分栏
```

## 折叠

```

Ctrl+Alt+[/]        折叠/展开

Ctrl+Alt+Shift+{/}  全局折叠/展开

Ctrl+K Ctrl+n       折叠n层
```

## 配置

```

Ctr+,               显示配置选项
```

## TreeView

```

Ctrl+0          切换TreeView焦点

Ctrl+\          切换TreeView显示



a               添加文件

m               移动文件

delete          删除文件
```