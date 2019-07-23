不建议使用树莓派安装kodi，因为卡的要死。



> 参考资料

- [Kodi 中文版开源多媒体影音中心播放器 - 打造家庭影院高清电影库必备软件神器](https://www.iplaysoft.com/kodi.html)

1. apt-cache search kodi-pvr
2. sudo apt-get install kodi-pvr-iptvsimple



## 安装树莓派

原先准备在ubuntu下安装，结果我从拼多多上买的SD读卡器在ubuntu上不好用，所以只能在我的windows上制作镜像文件了，在ubuntu上制作镜像文件，可以参考：[镜像制作](https://jingyan.baidu.com/article/636f38bb4f7af9d6b84610cd.html)



[也可以看官方文档](https://kodi.wiki/view/HOW-TO:Install_Kodi_on_Raspberry_Pi)



### 第一步：必要工具

> 软件

​	1：[树莓派](https://www.raspberrypi.org/downloads/raspbian/)

​	2：[etcher光盘制作工具](https://www.balena.io/etcher/)

​	3：[putty，http远程访问工具，如果你用windows的话](http://www.onlinedown.net/soft/2186.htm)

​	4：[vnc远程登录工具](https://www.realvnc.com/)

​	我用浏览器下载很慢，后来我就用小米路由器来下载，速度非常快。我下载的是`2019-07-10-raspbian-buster-full.img` 这个版本。



> 硬件

​	1：键盘、鼠标。

​	2：一个带hdmi的显示器。





### 第二步：制作镜像

将树莓派zip文件解压，并使用`etcher`写入SD卡。选择img文件，选择SD卡，然后点击`Flash`按钮。



![alt](E:/00-code/pi/wukong-kodi/doc/imgs/install-etcher.png)



### 第三步：基本配置



> 初次登录

- 选择语言

- 修改默认密码

- 连接无线网络，并登录到无线网络

- 屏幕自适应。

- 更新最新程序(可以跳过)

  

> 初始化配置

​	在进入树莓派的菜单中，选择`config`，启动下列内容设置成`enable`：

- SSH
- VCN



> 简单测试

前提：你要知道树莓派的IP地址。

- 使用putty登录到树莓派
- 使用vnc远程登录到树莓派



### 第四步：优化树莓派

如果不优化，感觉树莓派非常不好用

#### 配置共享文件夹

- [共享文件夹](https://www.cnblogs.com/xiangzhuo/p/9434117.html)

  

#### 解决鼠标不好用的问题

```shell
# 在其末尾先加上空格后，再加上<u>usbhid.mousepoll=0</u>
sudo vim /boot/cmdline.txt
sudo reboot now
```



#### 调整GPU

将GPU从64调整到256





### 第五步：如何找到树莓派IP

> 方法一

```shell
ping raspberrypi.local
```



> 方法二

```shell
arp -a
```

显示b开头的可能是树莓派





## 安装kodi



网上说要修改更新源，我也懒得弄了，直接执行下面得命令，不到5分钟就安装完毕了。

```shell
sudo apt-get install kodi
```



然后vcn 登录，打开kodi，可以看到版本是17.01





## 设置kodi



### 设置语言

[参考网址](https://www.jianshu.com/p/df475754acc1)

### 设置网络硬盘



### 设置直播TV



### 设置手机遥控



