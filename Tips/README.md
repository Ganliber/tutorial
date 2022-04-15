# Tips

[TOC]



> Record some error handling skills and solutions other than programming

## Linux

***

##### 开机时无法加载GUI

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

##### 普通用户不能使用sudo

进入root, 配置文件`/etc/sudoers`, 使root对其有写权限

```shell
chmod u+w /etc/sudoers
```

假设用户名为`stuart`,在`root ALL=(ALL:ALL) ALL`下方添加即可

```shell
stuart  ALL=(ALL) ALL
```





## Verbs

* `demo` : Demo源码可以理解为某种计算机语言的示例代码，是可以在相应的编译环境下直接运行的源代码，通常Demo的作用就是Demo源码开发者引导其他程序员进行二次开发所提供的模板程序代码。
* `high level` : 俯瞰的，全局概括性的，是在该方向的全局总览的角度；不是具体的，代码实例的















