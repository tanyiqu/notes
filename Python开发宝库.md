# Python开发宝库

## 静态方法

### 获取windows桌面路径

```python
import winreg

def getDesktop():
    key = winreg.OpenKey(winreg.HKEY_CURRENT_USER, r'Software\Microsoft\Windows\CurrentVersion\Explorer\Shell Folders')
    return winreg.QueryValueEx(key, "Desktop")[0]
    pass
```



## 问题处理

### pip安装使用清华源

```shell
pip install xxxx -i https://pypi.tuna.tsinghua.edu.cn/simple
```

