
## GUI和CLI
```bash
#切换桌面模式
$ init 5   #进入图形化界面
$ init 3   #进入命令介面

$ systemctl set-default graphical.target  #默认GUI
$ ln -sf  /lib/systemd/system/graphical.target  /etc/systemd/system/default.target  #方法二

$ systemctl set-default multi-user.target #默认CLI
$ ln -sf  /lib/systemd/system/multi-user.target  /etc/systemd/system/default.target  #方法二
```

## 图形化介面
```bash
$ yum grouplist  #显示系统已经安装的组件，和可以安装的组件

#安装Gnome
$ yum groupinstall -y 'X Window System'            #centos 安装 X window(如果系统安装之初采用最小化安装，那么先安装)
$ yum groupinstall -y 'GNOME Desktop Environment'   #centos 安装 GNOME桌面环境
$ yum groupinstall -y "GNOME Desktop"　
$ vim /etc/sysconfig/desktop  #设置默认桌面(方法一)
DESKTOP="GNOME"
$ echo "exec gnome-session" >> ~/.xinitrc #设置默认桌面(方法二)
$ startx  #开启图形界面

#安装KDE
$ yum groupinstall 'X Window System' -y  
$ yum groupinstall 'KDE (K Desktop Environment)' -y #centos下安装KDE桌面环境
$ vim /etc/sysconfig/desktop  #默认桌面选择 (方法一)
DESKTOP="KDE"
$ echo startkde >  .xinitrc  #默认桌面选择 (方法二)
$ startkde #启动桌面

#安装 xfce
$ yum groupinstall -y "X Window system"
$ yum install -y epel-release  # 安装额外包yum源（extra package for Enterprise Linux）
$ yum install -y lightdm
$ yum groupinstall -y xfce
$ vi /etc/lightdm/lightdm.conf
enable=true
port=177
$ systemctl disable gdm && systemctl enable lightdm  #将Display Manager切换为lightdm
$ systemctl start lightdm #启动lightdm

#切换桌面
$ switchdesk gnome
$ switchdesk kde

#卸载桌面
$ yum groupremove 'X Window System' -y          #卸载Xwindows
$ yum groupremove "GNOME Desktop Environment"   #卸载GNOME桌面环境
$ yum groupremove "KDE (K Desktop Environment)" #卸载KDE桌面环境 
```

## 安装中文字体
```bash
#文泉驿字体
$ yum list | grep wqy
$ yum install wqy*

#cjkuni字体
$ yum list | grep cjkuni 
$ yum install cjkuni*
```


## 配置网络
```bash
$ cd /etc/sysconfig/network-scripts
$ vi ifcfg-ens33
修改BOOTPROTO=static
添加IPADDR=192.168.1.60(这个根据自己的情况 而定，我的主机的ip是192.168.1.60，所以我的这个ip可以设置为192.168.1.（1~255之间的，但不能和宿主机或其他机器的ip重复）)
添加GATEWAY=192.168.1.1（这个是根据主机的默认网关一致的）
添加DNS1=192.168.1.1
添加子网掩码NETMASK=255.255.255.0
修改 ONBOOT="yes"
$ service network restart #重启服务
```


## Gnome操作
```bash
$ gsettings set org.gnome.nautilus.icon-view default-zoom-level small  #减小gnome图标尺寸

# 重新启动gnome-shell
alt+F2弹出界面
输入r重新启动gnome-shell

## Gnome重启
$ ps -ef|grep gnome-shell
$ kill -9 [进程号]
```

```bash
$ flatpak install  org.flameshot.Flameshot.flatpakref  #火烟截图
$ flatpak install https://flathub.org/repo/appstream/org.gimp.GIMP.flatpakref  #GIMP

```

