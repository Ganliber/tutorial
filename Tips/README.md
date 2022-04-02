# Tips

> Record some error handling skills and solutions other than programming

## Linux

***

* 开机时无法加载GUI

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

* 