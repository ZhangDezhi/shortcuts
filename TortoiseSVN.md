
```



```


```

#命令名称
TortoiseProc.exe  打开项目监视

#第一个参数: 命令
/command:about

#第二个参数: 路径
/path:"svn路径"

#第三个参数: 对话框(可以没有)
/closeonend:0 不自动关闭对话框
/closeonend:1 如果没发生错误则自动关闭对话框
/closeonend:2 如果没发生错误和冲突则自动关闭对话框
/closeonend:3如果没有错误、冲突和合并，会自动关闭

```

示例

```
$ TortoiseProc.exe /command:repobrowser /path:"https://172.16.4.236/svn/MAS平台软件/1_需求管理" /closeonend:0    #打开浏览器
$ TortoiseProc.exe /command:about   # 打开关于
$ TortoiseProc.exe /command:log /path:"https://172.16.4.236/svn/MAS平台软件/1_需求管理"   #直接查看日志
$ TortoiseProc.exe /command:log /path:"https://172.16.4.236/svn/MAS平台软件/1_需求管理" /closeonend:0  #不自动关闭

```