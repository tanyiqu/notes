# win10操作笔记

## 右键菜单添加cmd

添加注册表文件

```bash
Windows Registry Editor Version 5.00
[HKEY_LOCAL_MACHINE\SOFTWARE\Classes\Directory\background\shell\cmd_here]
@="在此处打开命令窗口"
"Icon"="cmd.exe"

[HKEY_LOCAL_MACHINE\SOFTWARE\Classes\Directory\background\shell\cmd_here\command]
@="\"C:\\Windows\\System32\\cmd.exe\""
```



## 右键菜单添加Windows Terminal

1. 确保电脑已经安装Windows Terminal
2. 记住自己的用户名，这里简单表示为**youruser**是
3. 准备一个图标，放在C:\Users\\**youruser**\AppData\Local\terminal 文件夹（需要新建）下，命名为**wt_32.ico**
4. 新建一个注册表文件内容如下，记得替换youruser为你自己的用户名

``` bash
Windows Registry Editor Version 5.00
[HKEY_LOCAL_MACHINE\SOFTWARE\Classes\Directory\background\shell\cmd_here]
@="在此处打开Windows Terminal"
"Icon"="C:\\Users\\youruser\\AppData\\Local\\terminal\\wt_32.ico"

[HKEY_LOCAL_MACHINE\SOFTWARE\Classes\Directory\background\shell\cmd_here\command]
@="C:\\Users\\youruser\\AppData\\Local\\Microsoft\\WindowsApps\\wt.exe"
```

