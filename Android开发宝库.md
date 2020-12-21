## 代码模板



## 独立方法



## 问题处理



## 其他

### App秒开启动图

1.新建一个Activity，取名为**SplashActivity**

2.在**res/drawable**下新建一个**splash.xml**文件

```xml
<?xml version="1.0" encoding="utf-8"?>
<layer-list xmlns:android="http://schemas.android.com/apk/res/android">
    <item>
        <!-- 图片 -->
        <bitmap
            android:gravity="fill"
            android:src="@drawable/ig_splash" />
    </item>
</layer-list>
```



3.设置主题

在**values/styles**里面添加如下

```xml
<style name="SplashTheme" parent="Theme.AppCompat.Light.DarkActionBar">
    <item name="android:windowBackground">@drawable/splash</item>
    <item name="android:windowFullscreen">true</item>
</style>
```



4.在**AndroidManifest.xml**中定义SplashActivity的theme为SplashTheme

```xml
<activity
          android:name=".activity.SplashActivity"
          android:theme="@style/SplashTheme">
    <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <action android:name="android.intent.action.VIEW" />

        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>
</activity>
```



5.修改**SplashActivity.java**

```java
public class SplashActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        startActivity(new Intent(this, MainActivity.class));//启动完主Activity就finish
        finish();
    }
}
```



6.这时候启动app就有秒开启动图的效果