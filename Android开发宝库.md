## 代码模板

### 剪贴板

```java
ClipboardManager clipboard = (ClipboardManager) getSystemService(Context.CLIPBOARD_SERVICE);
ClipData data = ClipData.newPlainText(null,str);
assert clipboard != null;
clipboard.setPrimaryClip(data);
```





<br>

## 独立方法

### 获取设备的目录

SD卡根目录

```java
public static String getSDCardPath() {
    return Environment.getExternalStorageDirectory().getAbsolutePath();
}
```



<br>

## 其他

### Android实现秒开效果

[Android实现秒开效果](https://www.cnblogs.com/tanyiqu/p/14168207.html)