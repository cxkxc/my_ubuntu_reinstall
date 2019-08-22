UBUNTU 安装 MAC OS
===================================

### 1. 为了修改GTK主题，图标，系统主题，光标，字体我们需要安装unity tweak。要安装unity tweak在ubuntu14.04上通过使用如下命令：
```Bash
sudo apt-get install unity-tweak-tool //安装unity-tweak-tool
```

### 2. 安装mac主题、图标、指针（2选1即可）
##### 主题1
```Bash
sudo add-apt-repository ppa:noobslab/macbuntu 
sudo apt-get update 
sudo apt-get install macbuntu-os-icons-lts-v7 //图标 
sudo apt-get install macbuntu-os-ithemes-lts-v7 //主题
```
##### 主题2
```Bash
sudo add-apt-repository ppa:noobslab/themes
sudo apt-get update
sudo apt-get install mac-ithemes-v3
sudo apt-get install mac-icons-v3
```

### 3. 安装plank Dock 插件（底部的菜单）（2选1即可）
##### 版本1
```Bash
sudo apt-get install plank //安装木板 
sudo add-apt-repository ppa:noobslab/macbuntu 
sudo apt-get update 
sudo apt-get install macbuntu-os-plank-theme-lts-v7 //安装plank主题
```
##### 版本2
```Bash
sudo add-apt-repository ppa:docky-core/ppa
sudo apt-get update
sudo apt-get install docky
```

### 4. 替换左上角的 Ubuntu Desktop 为 Mac OS X 
#### 想要修改成为Mac OS X，执行下面命令
```Bash
cd && wget -O Mac.po http://drive.noobslab.com/data/Mac-14.04/change-name-on-panel/mac.po
cd /usr/share/locale/en/LC_MESSAGES; sudo msgfmt -o unity.mo ~/Mac.po;rm ~/Mac.po;cd
```
#### 想改回来，执行下面的命令
```Bash
cd && wget -O Ubuntu.po http://drive.noobslab.com/data/Mac-14.04/change-name-on-panel/ubuntu.po
cd /usr/share/locale/en/LC_MESSAGES; sudo msgfmt -o unity.mo ~/Ubuntu.po;rm ~/Ubuntu.po;cd
```

### 5. 替换延迟滚动条为正常滚动条
#### 想要修改成为正常执行下面命令
```Bash
gsettings set com.canonical.desktop.interface scrollbar-mode normal
```
#### 想要改回来执行下面命令
```Bash
gsettings reset com.canonical.desktop.interface scrollbar-mode
```
### 以下项目有风险，请提前备份
### 以下项目有风险，请提前备份
### 以下项目有风险，请提前备份

### 6. 替换启动屏幕图片
#### 在这个小章节里面将会为ubuntu 14.04修改启动图片，包括载入动画跟苹果LOGO
#### 版本1
##### 安装
```Bash
sudo add-apt-repository ppa:noobslab/macbuntu 
sudo apt-get update 
sudo apt-get install macbuntu-os-bscreen-lts-v7
```
#### 修改回来
```Bash
sudo apt-get remove macbuntu-os-bscreen-lts-v7
```
#### 版本2
##### 安装
```Bash
sudo add-apt-repository ppa:noobslab/themes
sudo apt-get update
sudo apt-get install mbuntu-bscreen-v3
```
#### 想要修改回来
```Bash
sudo apt-get remove mbuntu-bscreen-v3
```

### 7. 修改 Ubuntu 的登录画面成为 Mac OS X 的样式
#### 版本1
##### 安装
```Bash
sudo add-apt-repository ppa:noobslab/macbuntu 
sudo apt-get update 
	sudo apt-get install macbuntu-os-lightdm-lts-v7
```
#### 修改回来
```Bash
sudo apt-get remove macbuntu-os-lightdm-lts-v7
```
######
#### 版本2
#### 安装
```Bash
sudo add-apt-repository ppa:noobslab/themes
sudo apt-get update
sudo apt-get install mbuntu-lightdm-v3
```
#### 修改回来
```Bash
sudo apt-get remove mbuntu-lightdm-v3
```

### 8. 去掉 ubuntu 锁屏的图标
#### 安装
```Bash
sudo xhost +SI:localuser:lightdm
sudo su lightdm -s /bin/bash
gsettings set com.canonical.unity-greeter draw-grid false;exit
sudo mv /usr/share/unity-greeter/logo.png /usr/share/unity-greeter/logo.png.backup
```
#### 修改回来
```Bash
sudo xhost +SI:localuser:lightdm
sudo su lightdm -s /bin/bash
gsettings set com.canonical.unity-greeter draw-grid true;exit
sudo mv /usr/share/unity-greeter/logo.png.backup /usr/share/unity-greeter/logo.png
```

### 9. 安装Mac字体（2选1）
#### 字体1
```Bash
wget -O mac-fonts.zip http://drive.noobslab.com/data/Mac-14.04/macfonts.zip
sudo unzip mac-fonts.zip -d /usr/share/fonts; rm mac-fonts.zip
sudo fc-cache -f -v
```
#### 字体2
```Bash
sudo apt-get install fonts-wqy-microhei //安装文泉驿微米黑字体
```

