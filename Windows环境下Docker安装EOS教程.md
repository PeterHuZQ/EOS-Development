# Windows环境下Docker安装EOS教程
---

## 1. Windows10下安装Docker的步骤
### 1.1、启用Hyper-V<br>
打开控制面板 - 程序和功能 - 启用或关闭Windows功能，勾选Hyper-V，然后点击确定即可，如图：
![](/picture/Hyper-V.png)<br>
点击确定后，启用完毕会提示重启系统，我们可以稍后再重启。

### 1.2、安装Docker
Docker下载地址为：https://store.docker.com/editions/community/docker-ce-desktop-windows<br>
下载完成后运行安装包，安装完成后界面，如图：
![](/picture/install_docker.png)<br>
单击Close and log out，这个时候我们重启一次电脑

### 1.3、启动Docker
* 在桌面找到Docker for Windows快捷方式，双击启动即可！
启动成功后托盘处会有一个小鲸鱼的图标。
打开命令行输入命令：`docker version`可以查看当前docker版本号，如图：<br>
![](/picture/start_docker.png)<br>


* 更换镜像源地址 <br>
Docker 路径更改<br>
网易镜像源地址为：http://hub-mirror.c.163.com<br>
点击托盘处docker图标右键选择-Settings，然后修改,如图：
![](/picture/change_image_resource.png)<br>
点击Apply后会重启Docker。

* 载入测试镜像测试
输入命名“docker run hello-world”可以加载测试镜像来测试，如图：
![](/picture/test_image.png)<br>
这样即表示安装成功了！

## 2. Docker安装EOS的步骤
### 2.1、构建 EOSIO 镜像
`git clone https://github.com/EOSIO/eos.git --recursive`<br>
`cd eos/Docker`<br>
`docker build . -t eosio/eos`<br>
![](/picture/build_eos.png)<br>

### 2.2、启动nodeos容器
`docker run --name nodeos -p 8888:8888 -p 9876:9876 -t eosio/eos nodeosd.sh arg1 arg2`<br>
![](/picture/start_nodeos.png)<br>

### 2.3、关闭区块

Docker有个图形化的容器管理工具，右下角Docker图标上点右键Kitematic，如果没有安装它会提示你去下载，是一个zip，告诉你下载完解压的位置“C:\Program Files\Docker\Kitematic”，放好之后就可以用图形化方式管理下载共享的Docker容器了, 容器安装完成可以启动、停止、重启、控制台操作，端口配置，存储位置配置等等。
左侧列表鼠标悬停出现X，点击X，关闭区块，如图：
![](/picture/kitematic.png)<br>










