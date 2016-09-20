# StartDialogImageView
【Android】Android开发启动app弹出一张广告图片，Dialog可以查看大图，查看某个图片功能

作者：程序员小冰，GitHub主页：https://github.com/QQ986945193 

新浪微博：http://weibo.com/mcxiaobing 

首先给大家看一下我们今天这个最终实现的效果图： 

![这里写图片描述](http://img.blog.csdn.net/20160919101351484)

首先说一下，这里利用的是一个dialog，然后设置我们需要的背景图，然后

在java主类中引用即可，当然这个功能，也可以放在查看某个图片的效果上面。

大家看情况集中到自己的项目中即可。下面给大家看一下java实现方法：

```
package startdialogimageview.qq986945193.startdialogimageview;

import android.app.Activity;
import android.app.Dialog;
import android.content.Context;
import android.graphics.Bitmap;
import android.graphics.BitmapFactory;
import android.os.Bundle;
import android.view.Display;
import android.view.Menu;
import android.view.View;
import android.view.View.OnClickListener;
import android.view.Window;
import android.view.WindowManager;
import android.widget.Button;
import android.widget.FrameLayout;
import android.widget.ImageView;
import android.widget.ImageView.ScaleType;
/**
 * @author ：程序员小冰
 * @新浪微博 ：http://weibo.com/mcxiaobing
 * @GitHub: https://github.com/QQ986945193
 * @CSDN博客: http://blog.csdn.net/qq_21376985
 * @码云OsChina ：http://git.oschina.net/MCXIAOBING
 */
public class MainActivity extends Activity {

    Dialog dia;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);


        Context context = MainActivity.this;
        dia = new Dialog(context, R.style.edit_AlertDialog_style);
        dia.setContentView(R.layout.activity_start_dialog);


        ImageView imageView = (ImageView) dia.findViewById(R.id.start_img);
        imageView.setBackgroundResource(R.mipmap.iv_android);
        dia.show();

        dia.setCanceledOnTouchOutside(true); // Sets whether this dialog is
        Window w = dia.getWindow();
        WindowManager.LayoutParams lp = w.getAttributes();
        lp.x = 0;
        lp.y = 40;
        dia.onWindowAttributesChanged(lp);
    }

}
```
所需要的style样式如下：

```
   <style name="edit_AlertDialog_style" parent="@android:style/Theme.Dialog">
        <item name="android:windowIsFloating">true</item>
        <item name="android:windowIsTranslucent">true</item>
        <item name="android:windowNoTitle">true</item>
        <!-- 是否启用标题栏 -->
        <item name="android:windowBackground">@android:color/transparent</item>
        <item name="android:background">@android:color/transparent</item>
        <item name="android:backgroundDimEnabled">true</item>
        <!-- 是否使用背景半透明 -->
    </style>
```
如果对您有帮助，欢迎star，fork。。。
