# Ubuntu

## 17.10 的Root登录

1. 为root创建密码
sudo passwd root  并输入两次密码

2. 进入/etc/pam.d/目录

    在目录内修改两个文件

    gdm-autologin

    gdm-password

    将两个文件的权限改成 777

     chmod 777 gdm-autologin

     chmod 777 gdm-password

    文件

    使用Vim或是Gedit修改上面的两个文件使用 # 注释里面的

    #auth        required        pam_succeed_if.so user != root quiet_success

    文件的原来的权限

     chmod 644 gdm-autologin

     chmod 644 gdm-password

    现在重新启动Ubuntu 17.10，并在开机的时候选择 【未列出？】输入用户名 root ，及你第一步设置   密码，好了现在你可以以Root登录了。


##  root 用户没有声音


1. 短暂开启（本次登陆开启）

    终端运行下面命令：

         pulseaudio --start --log-target=syslog


2. 永久开启（每次登陆自动开启）
        
         vi /root/.profile
        新增一行，加上pulseaudio --start --log-target=syslog

