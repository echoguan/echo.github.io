---
title: iTerm2 配色方案
categories: 技术
date: 2018-07-04 08:46:01
tags: 工具
---



> 记录自己配置过程

#### 效果图





#### 配置

1. 设置 iTerm2 为**默认终端**：
   - （菜单栏）iTerm2 -> Make iTerm2 Default Term 
2. 全局热键启动和关闭 iTerm2：
   - 偏好设置 preferences -> Keys -> 勾选 Hotkey 下的 Show/hide iTerm2 with a system-wide hotkey，将热键设置为command+i
3.  Mac OS X 上修改主机名：`sudo scutil --set HostName MacBookPro`
4. 透明度：偏好设置 preferences -> Profiles，右侧找到window选项卡，拖动Transparency调整。



#### 配色方案

- 我选用的是 [solarized](http://ethanschoonover.com/solarized)，点开官网，下载，解压。
- 然后打开 iTerm2 下的偏好设置 preference ，点开 profiles 下的 colors 选项，点击右下角的 Color Presets  选项，选择 import ，导入解压到的 solarized 文件下的 Solarized Dark.itermcolors。
- 然后勾选 Solarized Dark。



#### 安装 [oh-my-zsh](http://ohmyz.sh/) 

1. 命令行输入 `sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
2. `nano ~/.zshrc`，修改为 `ZSH_THEME="ys"`



#### 插件

1. [incr.zsh](https://link.jianshu.com/?t=http://mimosa-pudica.net/zsh-incremental.html) 自动补齐插件
2. highlight 插件