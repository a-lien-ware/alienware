# alienware  
## Ubuntu  
### Ubuntu25.04中可能会有许多问题一次解答一下:  
[Steam++](https://steampp.net),无法正常加速?  
在加速模式里面选择```system```模式  

---
crcpy无法使用?  
终端运行以下代码将将其卸载  
```bash
sudo apt remove --purge scrcpy
sudo apt autoremove
```
不要卸载```adb```和```fastboot```,在[Github](https://github.com)上下载最新软件,然后将其解压到```/opt/```目录中,运行  
```bash
sudo ln -s /opt/*scrcpy目录*/scrcpy /usr/bin/scrcpy
```
然后在终端运行```scrcpy```就可以了,如果想要添加到启动器或者桌面可以运行  
```bash
sudo echo "[Desktop Entry]\nName=Scrcpy\nExec=scrcpy\nIcon=/opt/*scrcpy目录*/icon.png\nTerminal=false\nType=Application" >> ~/.local/share/applications/scrcpy.desktop
```
如果想要添加到桌面则运行  
```bash
sudo mv ~/.local/share/applications/scrcpy.desktop 桌面/
sudo chmod +x scrcpy.desktop
```

---
gimp无法切换中文,到[官网](https://www.gimp.org/downloads/),点击Applmage的那个,然后下载到/opt/gimp/目录中,然后运行  
```bash
sudo chmod +x *下载文件名*
sudo ln -s /opt/gimp/*下载文件名* /bin/gimp
```
然后添加到桌面或者启动台的步骤和上面类似,把两个```scrcpy```改为```gimp```,把```Icon```删除或者自己找图片放到```/opt/gimp```目录下,改为相关路径,然后就可以了,但是打开的时候可能会有点慢  

---
如何配置c++开发环境?  
```bash
sudo apt install build-essential g++
sudo snap install code --classic
```
然后可以编写一个C++程序验证以下
```cpp
#include <iostream>  // 引入输入输出流库

int main() {
    std::cout << "Hello, World!" << std::endl;  // 输出 Hello, World!
    return 0;  // 返回 0 表示程序正常结束
}
```
然后在终端当前目录下运行  
```bash
g++ main.cpp -o main
./main
```
如果输出为
```bash
Hello,World!
```
则表示配置成功

---
如何配置qt开发环境?  
```bash
sudo apt install qtcreator qt5-default build-essential
```
---
AppImage文件无法正常使用  
可以尝试在运行文件时候加上```--appimage-extract```来解压文件  
检查依赖  
```bash
sudo apt install libfuse2
```
然后调整权限  
```bash
sudo chown root:root "追踪或断点陷阱 (核心已转储)报错的路径"
sudo chmod 4755 "追踪或断点陷阱 (核心已转储)报错的路径"
```
然后重新运行就可以了  

---
网页版本windows12  
在右侧下载win12.tar.gz之后解压下载，双击目录下面的desktop.html就可以了

---
许多软件的问题可能都是因为系统版本与软件版本不匹配,可以到官网下载最新版本安装就可以了
