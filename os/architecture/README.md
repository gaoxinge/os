# architecture

## 1

## 2

### linux

#### 基础

- [linus](https://github.com/torvalds)
- [linux](https://github.com/torvalds/linux)

#### 教程

- [菜鸟教程](http://www.runoob.com/linux/linux-tutorial.html)
- [鸟哥的Linux私房菜：基础学习篇](https://www.gitbook.com/book/wizardforcel/vbird-linux-basic-4e/details)
- [鸟哥的Linux私房菜：服务器架设篇](https://www.gitbook.com/book/wizardforcel/vbird-linux-server-3e/details)
- [Linux工具快速教程](http://linuxtools-rst.readthedocs.io/zh_CN/latest)

### windows

#### C盘

##### Program Files/Program Files (x86)

- [x64 x86有啥区别](http://jingyan.baidu.com/article/fa4125acb30e8228ac709232.html)
- [program files文件夹和program files(x86)文件夹](http://zhidao.baidu.com/question/196893113.html?fr=iks&word=program+files%BA%CDprogram+files%28x86%29&ie=gbk)

##### ProgramData

- 略

##### Windows

- 注册表
  - [Windows注册表内容详解](http://blog.sina.com.cn/s/blog_4d41e2690100q33v.html)
- 任务管理器
  - 任务管理器用于监控进程，线程，位于`C:\Windows\SysWOW64\taskmgr.exe`
- 微软管理控制台
  - 微软管理控制台可以删增SSL证书，位于`C:\Windows\SysWOW64\mmc.exe`

##### 用户

- 略

#### 控制面板

##### 入门/疑难解答/备份和还原/恢复/操作中心

- 略

##### Windows Defender/Windows Update/Windows防火墙

- [怎么关闭windows的自动更新功能](http://jingyan.baidu.com/article/5553fa820914e365a3393472.html)
- [如何关闭win7防火墙](http://jingyan.baidu.com/article/cd4c2979d55c41756e6e60a1.html)

##### 区域和语言/时间和日期/字体/颜色管理/自动播放/桌面小工具/语音识别

- 略

##### 任务栏和[开始]菜单/通知区域图标

- 略

##### 用户账户/家庭组/家长控制

- 略

##### 程序和功能/默认程序/索引选项/文件夹选项

- 略

##### 管理工具

- Windows PowerShell Modules
  - [PowerShell Team](https://github.com/PowerShell)
  - [PowerShell 在线教程](http://www.pstips.net/powershell-online-tutorials)

##### 计算机管理

- 计算机管理内设有设备管理器

##### 设备管理器/性能信息和工具/轻松访问中心/windows移动中心

- 设备管理器用于管理驱动

##### 鼠标/键盘/设备和打印机/显示/声音

- 略

##### Internet选项

- Internet选项在IE和Chrome等浏览器内均可打开

##### Windows CardSpace/凭据管理器

- [Win 7密码管家之凭据管理器](http://jingyan.baidu.com/article/e75aca85b5de36142fdac666.html)

##### 网络和共享中心/电话和调制解调器

- 网络和共享中心可以查看完整映射，但是需要把公用网络改成家庭网络或者工作网络

##### 位置和其他传感器/生物特征设置

- 生物特征设置用于指纹识别

##### 电源选项/同步中心

- 略

#### 虚拟机

##### virtualbox

- [官网](https://www.virtualbox.org)
- [如何在VirtualBox中安装Ubuntu虚拟机](http://www.crifan.com/virtualbox_install_ubuntu_virtual_machine)

##### vmware

- [官网](http://www.vmware.com/cn.html)
- [Linux学习笔记——vmware player中安装ubuntu](http://blog.csdn.net/xukai871105/article/details/25076531)

##### docker

- [官网](http://www.docker.com)
- [Github](https://github.com/docker/docker)
- [docker中文社区](http://www.docker.org.cn/index.html)
- [菜鸟教程](http://www.runoob.com/docker/docker-tutorial.html)
- [docker入门实战](http://yuedu.baidu.com/ebook/d817967416fc700abb68fca1?fr=aladdin&key=docker)
- [Docker — 从入门到实践](https://www.gitbook.com/book/yeasy/docker_practice/details)
  
##### ubuntu

- 介绍
  - [官网](https://www.ubuntu.com/index_kylin)
  - [教程](https://github.com/gaoxinge/os/blob/master/linux/%E6%95%99%E7%A8%8B.md)
- 命令

```
docker pull ubuntu
docker run -it ubuntu
```

##### python

- 介绍
  - [官网](https://www.python.org)
  - [教程](https://github.com/THM-TheoreM/Python)
- 命令

```
docker pull python:3.5
docker run -it python:3.5
docker run -v $PWD/myapp:/usr/src/myapp -w /usr/src/myapp python:3.5 python helloworld.py

# myapp/helloworld.py
# print("Hello World!")

# -v $PWD/myapp:/usr/src/myapp：把$PWD/myapp路径映射到/usr/src/myapp路径
# -w /usr/src/myapp：指定/usr/src/myapp为工作目录
# python:3.5：即docker run python:3.5
# python helloworld.py：运行helloworld.py
```

##### tensorflow

- [官网](https://www.tensorflow.org)
- [Github](https://github.com/tensorflow)
- [中文社区](http://www.tensorfly.cn)
- [miniflow](https://github.com/tobegit3hub/miniflow)
- [TensorFlow实战](https://book.douban.com/subject/26974266/)
- [Tensorflow：实战Google深度学习框架](https://book.douban.com/subject/26976457/)
- [models](https://github.com/tensorflow/models)
- [stanford tensorflow tutorials](https://github.com/chiphuyen/stanford-tensorflow-tutorials)
- [EffectiveTensorflow](https://github.com/vahidk/EffectiveTensorflow)
- [TensorFlow World](https://github.com/astorfi/TensorFlow-World)
- [TensorFlow Examples](https://github.com/aymericdamien/TensorFlow-Examples)
- [TensorFlow Tutorials](https://github.com/nlintz/TensorFlow-Tutorials)
- [Tensorflow 101](https://github.com/sjchoi86/Tensorflow-101)
- [TensorFlow白皮书](http://www.jianshu.com/p/65dc64e4c81f)
- [超智能体](https://www.gitbook.com/book/yjango/superorganism/details)
- [小石头的码疯窝](http://hacker.duanshishi.com/?cat=18)
- [如何搭建一台深度学习服务器](http://blog.csdn.net/jbddygb/article/details/53333800)
- [个人深度学习环境搭建（一）：前言](http://www.jianshu.com/p/e50e9a5c2f2b)

##### hadoop

- [官网](http://hadoop.apache.org)
- [Github](https://github.com/apache/hadoop)
- [教程](./2/windows/虚拟机/hadoop/教程)
- [Hadoop家族学习路线图](http://blog.fens.me/hadoop-family-roadmap)
- [Hadoop学习笔记系列文章导航](http://www.cnblogs.com/edisonchou/p/4440107.html)
