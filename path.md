# 系统特殊路径
## Windows
```
%AppData%\Microsoft\Windows\Start Menu\Programs\Startup            | 自启动目录 (用户)
C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp       | 自启动目录 (系统)
%AppData%\Microsoft\Windows\SendTo                                 | 发送到目录
```
## Linux

``` 
/
/bin
/boot
/dev
/etc
/home
/lib
/lost+found
/mnt
/opt
/proc
/root
/sbin
/tmp
/usr
/var

/usr/share/backgrounds/   壁纸位置
/usr/share/pixmaps/   GNOME 自带的图片一般在
```


## macOS 

================================================================== 系统:
$TMPDIR    |   临时目录
/dev                            | 包含设备的文件装载点
/bin                            | 系统基本命令集 ,bash也在其中
/Volumes                        | 系统默认的磁盘装载点
/usr/bin/emacs                  | emacs 路径:
/private/var                    | 用户数据库、root用户目录、虚拟内存、日志等
/Library/Updates                | AppStore update路径
/usr/bin 和 usr/libexec         | OS X 系统可执行文件
/private/etc 或 etc/            | 系统级的配置和数据库等文件
/System/Library/Extensions/     | 设备驱动文件夹
/Library/PrivilegedHelperTools/ | 系统权限路径

/System/Library/CoreServices/CoreTypes.bundle/Contents/Resources/ | 系统图标位置
/System/Library/CoreServices/SystemFolderLocalizSations/           | 本地话语言路径
===brew=============================                              |
/usr/local/Cellar/                                                | brew 安装路径
~/Library/Caches/Homebrew/downloads                               | brew下载路径
===插件=====================================                      |
/资源库/QuickLook/                                                | QuickLook插件位置  QuickLook插件包一般是.qlgenerator 格式
/Library/PreferencePanes/                                         | 控制面板程序
/System/Library/Input Methods/KeyboardViewer.app                  | mac桌面软键盘位子
~/资源库/Services/                                                | 鼠标邮件服务_>菜单
~/Library/Caches/Metadata/Safari                                  | Safari 书签和History位置:
~/Library/Application Support/Snippets                            | Snippets保存路径:
~/Library/Screen Savers                                           | 屏保存储路径
~/Library/Logs/DiagnosticReports/                                 | mac crash 报告位置:
============================================XCode=============    |
~/Library/Application Support/Developer/Shared/Xcode/Plug-ins/    | Xcode插件路径
~/Library/Application support/Developer/Shared/Plug-ins           | xcode插件位置
~/Library/Developer/Xcode/DerivedData                             | Xcode应用缓存路径
~/Library/Developer/Xcode/iOS DeviceSupport/                      | iOS模拟器
~/Library/Developer/Xcode/UserData/CodeSnippets                   | 代码自动(codeSnippets)完成路径



===应用:
/Users/zhangdezhi/Library/Containers/com.apple.BKAgentService/Data/Documents/iBooks/Books                        | iBook存储路径
/Users/zhangdezhi/Library/Containers/com.amazon.Kindle/Data/Library/Application Support/Kindle/My Kindle Content | Kindle.app 文件路径
/Users/zhangdezhi/Library/Containers/com.syniumsoftware.macfamilytree7/Data/Backups/示例家谱                     | MacFamilyTree 备份路径:
/Users/zhangdezhi/Library/Containers/com.tencent.xinWeChat/Data/Library/Application Support/com.tencent.xinWeChat/2.0b4.0.9/d449f68ed8aa1312576bff232f9e3ce3 |微信文件位子

卸载某些应用程序后会留下一些预置文件和缓存等
~/Library/Application Support/(应用程序名称)
~/Library/Preferences/(应用程序名称)
~/Library/Caches/(应用程序名称)

特殊文件:
/etc/gitconfig  | 系统中所有用户的配置文件 使用 git config时候 使用 --system
~/.gitconfig    | Git配置文件路径(该用户全局的) 使用 git config时候 使用 --global
 .git/config    | 只针对当前目录有效
~/.bash_profile | 终端重定义指令文件路径
