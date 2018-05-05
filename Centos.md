# centos 3.22.2

root 无法打开Chromium

    cd /use/share/applications/
    找到图标右建属性
    /usr/bin/chromium-browser %U --no-sandbox

root登陆
对于CentOS 7的用户,简单来说就是：vi /etc/gdm/custom.conf
    [daemon]
    AutomaticLoginEnable=True
    AutomaticLogin=root  #你想自动登录的用户名