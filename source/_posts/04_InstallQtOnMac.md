---
title: 在Mac上快速搭建qt环境的方法
date: 2017-12-23 19:20:10
tags: [qt,homebrew]
category: TECH

---

<!-- abstract -->
<!-- HTML 方式的居中 -->
<blockquote class="blockquote-center">
	在mac上使用brew ／ brew cask 快速搭建Qt开发环境
</blockquote>

<!-- more -->

<!-- context -->


---
## 工具
Mac上的包管理工具：brew 
及其补充版 brew cask
具体介绍请戳：[官网](https://brew.sh/index_zh-cn.html)/[知乎](https://www.zhihu.com/question/22624898)

---
### Step 0 （已安装homebrew 的跳过）
安装 homebrew:	

	/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" 
	
homebrew 使用方法：

	$ brew --help
	
	Example usage:
	  brew search [TEXT|/REGEX/]
	  brew (info|home|options) [FORMULA...]
	  brew install FORMULA...
	  brew update
	  brew upgrade [FORMULA...]
	  brew uninstall FORMULA...
	  brew list [FORMULA...]
	
	Troubleshooting:
	  brew config
	  brew doctor
	  brew install -vd FORMULA
	
	Developers:
	  brew create [URL [--no-fetch]]
	  brew edit [FORMULA...]
	  https://docs.brew.sh/Formula-Cookbook.html
	
	Further help:
	  man brew


---
### Step 1 (安装qt和qt-creator)
安装 qt：
	
	brew install qt
	
在博主电脑上的效果（当前最新版是qt5.10）：

	$ brew install qt
	
	Updating Homebrew...
	==> Auto-updated Homebrew!
	Updated 1 tap (caskroom/cask).
	No changes to formulae.
	
	==> Downloading https://homebrew.bintray.com/bottles/qt-5.10.0.el_capitan.bottle
	Already downloaded: /Users/[userName]/Library/Caches/Homebrew/qt-5.10.0.el_capitan.bottle.tar.gz
	==> Pouring qt-5.10.0.el_capitan.bottle.tar.gz
	==> Caveats
	We agreed to the Qt opensource license for you.
	If this is unacceptable you should uninstall.
	
	This formula is keg-only, which means it was not symlinked into /usr/local,
	because Qt 5 has CMake issues when linked.
	
	If you need to have this software first in your PATH run:
	  echo 'export PATH="/usr/local/opt/qt/bin:$PATH"' >> ~/.bash_profile
	
	For compilers to find this software you may need to set:
	    LDFLAGS:  -L/usr/local/opt/qt/lib
	    CPPFLAGS: -I/usr/local/opt/qt/include
	For pkg-config to find this software you may need to set:
	    PKG_CONFIG_PATH: /usr/local/opt/qt/lib/pkgconfig
	
	==> Summary
	🍺  /usr/local/Cellar/qt/5.10.0: 9,351 files, 291.7MB
	
---
安装 qt-creator:

	brew cask install qt-creator
	
博主电脑安装效果：

	$ brew cask install qt-creator
	
	==> Satisfying dependencies
	==> Downloading http://download.qt.io/official_releases/qtcreator/4.5/4.5.0/qt-c
	######################################################################## 100.0%
	==> Verifying checksum for Cask qt-creator
	==> Installing Cask qt-creator
	==> Moving App 'Qt Creator.app' to '/Applications/Qt Creator.app'.
	🍺  qt-creator was successfully installed!
	
### Step 2 (配置Qt kits) 

＃**新安装的qt－creator需要配置qmake的路径：**

*Qt－Creator* 程序里面依次打开：
**Qt-Creator**-> **偏好设置** -> **构建和运行** -> **Qt Version** -> **添加..**  -> 弹出对话框、点***cmd+shift＋g*** 、输入**/usr/local/Cellar/qt/5.10.0/bin** -> 选中qmake -> 确认

在 默认的构建套件（kit） 里面选上 新安装 **Qt版本:** 即可。









