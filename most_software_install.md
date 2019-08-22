### 0. 换源(应用商店换源)
```Bash
sudo apt-get update
```

### 1. 输入法安装 （下载安装包）
```Bash
sudo dpkg -i sogoupinyin_2.2.0.0102_amd64.deb 
sudo apt-get -f install
sudo dpkg -i sogoupinyin_2.2.0.0102_amd64.deb 
```
重启


### 2. 浏览器升级
-->中文
```Bash
sudo apt-get install firefox-locale-zh-hans
```
-->账号同步

同时，复制图片、下载、my_ws



### 3. terminal
-->编辑-首选项：添加到原始标题之后，背景图片
-->编辑-快捷键：复制、黏贴、放大、缩小



### 4. 卸载libreoffice系列软件：
在软件中心-已安装，找libreoffice开头的软件，卸载；
卸载Amazon链接；
下载vlc；
下载unity-tweak-tool 0.0.6ubuntu2~ubuntu14.04.1；
打开dash，输入snap搜到ubuntu自带的截图程序，拖动到启动器里固定
打开dash，搜索system monitor，找到ubuntu的任务管理器，拖动到启动器固定




### 5. 安装wps



### 6. 主题设置（应用商店下载 unity-tweak-tool ）
```Bash
https://github.com/anmoljagetia/Flatabulous //-->下载主题
unzip mv Flatabulous-master  //-->解压
sudo mv Flatabulous-master /usr/share/themes/    //-->复制
```
-->打开APP，选择主题、图标，启动器图标大小36，热区



### 7. qt安装
```Bash
cd Downloads/my_software_package
chmod +x qt-opensource-linux-x64-5.7.0.run 
./qt-opensource-linux-x64-5.7.0.run 
```
一路next。。。

### 8. opencv安装配置


### 9.gedit 配置


### 10.flash安装
```Bash
// 1、下载
//2. 將下载好的包拷到某个目录下并解压得到文件，得到如下libflashplayer.so文件与usr文件夹
cd /home/kxc/下载/my_software_package/flash_release
//3. 将libflashplayer.so拷到firefox的插件目录/usr/lib/mozilla/plugin/下
sudo cp libflashplayer.so /usr/lib/mozilla/plugins
//4. 将usr/目录下所有文件拷到/usr下
sudo cp -r usr/* /usr
```




