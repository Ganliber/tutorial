# Tips

[TOC]



> Record some error handling skills and solutions other than programming

## Linux

***

### 开机时无法加载GUI

> Ubuntu 20.04 出现错误, 开机卡在了启动图形界面之前

```
/dev/nvme0n1p7:clean, xxxxx/xxxxx files, xxxxx/xxxxx blocks
```

解决办法：[参见博客](https://blog.csdn.net/Machine_yan/article/details/109736020)

进入命令行

```
Ctrl+Alt+F2(也可能是 Ctrl+Alt+Fn+F2 ),输入用户名密码登录
```

最好切换到root权限

```
su root
```

修改`grub`文件

```
(root) vim etc/default/grub
```

更新

```
(root) update-grub
```

重新启动

```
reboot
```

##### 如果github遇见fatal

```
fatal : unable to access ...
```

可以把代理关掉之后再试，且以`ssh`为主

##### Linux 上下左右键不能用了

```shell
bash
```

进入bash模式即可

### 普通用户不能使用sudo

进入root, 配置文件`/etc/sudoers`, 使root对其有写权限

```shell
chmod u+w /etc/sudoers
```

假设用户名为`stuart`,在`root ALL=(ALL:ALL) ALL`下方添加即可

```shell
stuart  ALL=(ALL) ALL
```

### linux 磁盘容量不够

扩容：[Ubuntu磁盘扩容](https://blog.csdn.net/qq_46170379/article/details/116808669?spm=1001.2101.3001.6650.3&utm_medium=distribute.pc_relevant.none-task-blog-2~default~CTRLIST~default-3.fixedcolumn&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~CTRLIST~default-3.fixedcolumn)

<img src="C:\Users\XiZhongKuiYue\AppData\Roaming\Typora\typora-user-images\image-20220419235211210.png" alt="image-20220419235211210" style="zoom:50%;" />

成功！

## Verbs

* `demo` : Demo源码可以理解为某种计算机语言的示例代码，是可以在相应的编译环境下直接运行的源代码，通常Demo的作用就是Demo源码开发者引导其他程序员进行二次开发所提供的模板程序代码。
* `high level` : 俯瞰的，全局概括性的，是在该方向的全局总览的角度；不是具体的，代码实例的





## Windows

### 快捷键

* `win + shift + S`截图，可以找到粘贴板打开后编辑







## Docker

***

* Docker 配 VSCode

  > 打开本地Docker，打开VSCode进入docker然后右键点击相应容器如`ubuntu:20.04` ---> `attach shell`即可连接docker 的命令行`CLI`





## VM connected by vscode

***

> 关于参考链接，越靠下越靠谱（目前来说都解决了，只需要把`Git\usr\bin\ssh.exe`作为`vscode`的相应的`remote.ssh.path`即可）

* Link-> [Virtual Machine Connected by VSCode](https://www.cnblogs.com/hi3254014978/p/12681594.html)

  关于virtualbox的-> [VirtualBox connection configure](https://www.littlezhang.com/2019/08/%E4%BD%BF%E7%94%A8vscode-ssh%E8%BF%9E%E6%8E%A5linux%E8%99%9A%E6%8B%9F%E6%9C%BA/)

  有效的方案 -> [VirtualBox and vscode build develop environment](https://blog.ceba.tech/2019/05/Development-with-VM-VSCode/index.html)

* 安装`extension` --> `Remote-SSH`
* 打开`>ssh setting`，勾选`Remote.SSH:Show Login Terminal`

### 关于VitualBox的配置Configure

* 设置->网络->(选择一个NAT连接模式的网卡)高级->新建一个TCP连接->自定义主机端口和用户端口
* vscode 中的 Port 设置为自定义的主机端口



### error:写入管道不存在

详细的看了一下vscode的报错日志，才知道原来是本地的known_hosts文件记录服务器信息与现服务器的信息冲突了，导致连接失败。

解决办法：
删除`C:/User/xxx/.ssh/known_hosts`文件，然后重新连接即可。



### 关键问题解决

> 将默认的`ssh.exe`切换成`git`安装目录下的`ssh.exe`，因为这个才是基于`linux`环境的！！！！！

更改方法

* vscode:

  * Remote.ssh.path改为`git安装目录\Git\usr\bin\ssh.exe`

* 配置即可

  * 注意默认连接端口是 22

* ubuntu 中的 git 版本可能较低，以下是更新 git 版本的方法

  ```bash
  sudo apt update  # 更新源
  sudo apt install software-properties-common # 安装 PPA 需要的依赖
  sudo apt-get install --reinstall ca-certificates # 使得ppa能够被识别
  sudo add-apt-repository ppa:git-core/ppa    # 向 PPA 中添加 git 的软件源
  sudo apt-get update
  sudo apt-get install git # 更新git
  
  git --version # 
  ```

* 出现以下结果即说明连接成功，此时只需要在---资源管理器---中选择相应的文件夹即可纵享丝滑。

  <img src="D:\github\tutorial\image\vscode_connecting_virtualbox_success.png" alt="image-20220524150834365" style="zoom: 50%;" />





