# alienware  
## Ubuntu  
### Ubuntu25.04中可能会有许多问题一次解答一下:  
1.[Steam++](https://steampp.net),无法正常加速?  
在加速模式里面选择```system```模式  

---
2.scrcpy无法使用?  
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
3.gimp无法切换中文,到[官网](https://www.gimp.org/downloads/),点击Applmage的那个,然后下载到/opt/gimp/目录中,然后运行  
```bash
sudo chmod +x *下载文件名*
sudo ln -s /opt/gimp/*下载文件名* /bin/gimp
```
然后添加到桌面或者启动台的步骤和上面类似,把两个```scrcpy```改为```gimp```,把```Icon```删除或者自己找图片放到```/opt/gimp```目录下,改为相关路径,然后就可以了,但是打开的时候可能会有点慢  

---
许多软件的问题可能都是因为系统版本与软件版本不匹配,可以到官网下载最新版本安装就可以了
