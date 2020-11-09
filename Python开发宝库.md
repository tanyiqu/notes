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



### 删除文件夹及其文件

```python
import shutil

def rmDir(dirPath: str):
    shutil.rmtree(dirPath)
    pass
```



## 问题处理

### pip安装使用清华源

```shell
pip install xxxx -i https://pypi.tuna.tsinghua.edu.cn/simple
```



### 标记方法过时

```python
def my_function(x, y):
	# 添加这一行代码
    warnings.warn("my_function is deprecated", DeprecationWarning)
    return x + y
```

