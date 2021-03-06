安装OpenCV 2.4.10
===================================
### 1. 先从sourceforge上下载OpenCV的源码
```Bash
http://jaist.dl.sourceforge.net/project/opencvlibrary/opencv-unix/2.4.10/opencv-2.4.10.zip
```

### 2. 解压到任意目录
```Bash
unzip opencv-2.4.10.zip
```

### 3. 进入源码目录，创建release目录
```Bash
cd opencv-2.4.10
mkdir release
```

### 4. 可以看到在OpenCV目录下，有个CMakeLists.txt文件，需要事先安装一些软件
```Bash
sudo apt-get install build-essential cmake libgtk2.0-dev pkg-config python-dev python-numpy libavcodec-dev libavformat-dev libswscale-dev
```

### 5.  进入release目录，安装OpenCV是所有的文件都会被放到这个release目录下
```Bash
cd release
```

### 6. cmake编译OpenCV源码，安装所有的lib文件都会被安装到/usr/local目录下
```Bash
cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local ..
```

### 7. 安装
```Bash
sudo make install
```

### 8. 测试，在某个目录下建立一个test.cpp文件
```c++
#include <cv.h>
#include <highgui.h>

using namespace cv;

int main(int argc, char* argv[])
{
    Mat image;
    image = imread(argv[1], 1);
  
    if (argc != 2 || !image.data)
    {
        printf("No image data\n");
        return -1;
    }

    namedWindow("Display Image", CV_WINDOW_AUTOSIZE);
    imshow("Display Image", image);
    waitKey(0);
    return 0;
}
```

### 9. 写一个cmake的makefile，也叫CMakeLists.txt
```Bash
project(test)
find_package(OpenCV REQUIRED)
add_executable(test test)
target_link_libraries(test ${OpenCV_LIBS})
cmake_minimum_required(VERSION 2.8)
```

### 10. 编译+运行
（请注意camke的后面还有一个点）
```Bash
cmake .
make
```
得到可执行文件test


### 11.  随便弄个jpg图片做个测试，注意要和上面那个可执行文件放在同一目录下面,我这里名字取的是test.jpg。
### 12.  如果能看到照片，那就表示成功了。
 ```Bash
 ./test test.jpg
```
========================================================

[qt出现：libopencv_core.so.2.4: cannot open shared object file: No such file or direc]！！！
======================================================================
### 配置opencv的环境变量
#### 打开opencv.conf文件：
```Bash
sudo gedit /etc/ld.so.conf.d/opencv.conf
```
#### 在打开的opencv.conf文件中写入
```Bash
/usr/local/lib
```
#### 保存退出，执行
```Bash
sudo ldconfig
```
#### 打开bash.bashrc文件：
```Bash
sudo gedit /etc/bash.bashrc
```
#### 在打开的bash.bashrc文件的最后加入如下内容：
```Bash
PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/usr/local/lib/pkgconfig export PKG_CONFIG_PATH
```




