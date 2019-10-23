# Curtain
 [![Hex.pm](https://img.shields.io/badge/download-0.0.4-green)](https://bintray.com/beta/#/soulqw/AndroidFrame/curtain?tab=overview)
 [![Hex.pm](https://img.shields.io/badge/Jetpack-AndroidX-orange)]()
 [![Hex.pm](https://img.shields.io/hexpm/l/plug.svg)](https://www.apache.org/licenses/LICENSE-2.0)
#### 一个更简洁好用的高亮蒙层库：
 - 一行代码完成某个View,或者多个View的高亮展示
 - 自动识别圆角背景,也可以自定义高亮形状
 - 高亮区域支持自定义大小、操作灵活
 - 顺应变化,基于Android X
 - 配置简单，导入方便
 
 ![image](https://img-blog.csdnimg.cn/20191009181206920.png)

## Installation：

```java
dependencies {
    implementation 'com.qw:curtain:0.0.4'
}

```
## Usage：
- 仅仅是高亮某个View
```java
    private void showCurtain(){
        new Curtain(MainActivity.this)
                .with(findViewById(R.id.textView))
                .show();
    }
```
![image](https://upload-images.jianshu.io/upload_images/4346197-92c1944753653bbe.png)

- 如果你希望那个view的蒙层区域更大一些:

```java
   private void showCurtain(){
        new Curtain(MainActivity.this)
                .with(findViewById(R.id.textView))
                .withPadding(findViewById(R.id.textView),24)
                .show();
    }

```
- 也可以同时高亮多个View:

```java
  private void showCurtain(){
        new Curtain(MainActivity.this)
                .with(findViewById(R.id.textView))
                .with(findViewById(R.id.imageView))
                .show();
    }
```
![image](https://upload-images.jianshu.io/upload_images/4346197-a5b0376674a7b373.png)

- 如果你在蒙层上加上一些其他的元素,可以额外传入View布局:

```java
   private void showCurtain(){
        new Curtain(MainActivity.this)
                .with(findViewById(R.id.textView))
                .setTopView(R.layout.nav_header_main)
                .show();
    }
```
![image](https://upload-images.jianshu.io/upload_images/4346197-f0f7453aae3cec80.png)

- 如果你想监听蒙层的展示或者消失的回调:

```java
   private void showCurtain(){
        new Curtain(MainActivity.this)
                .with(findViewById(R.id.imageView))
                .setCallBack(new Curtain.CallBack() {
                    @Override
                    public void onShow(IGuide iGuide) {

                    }

                    @Override
                    public void onDismiss(IGuide iGuide) {

                    }
                }).show();
    }
```
- 其他一些功能介绍:

```java
    private void showCurtain() {
        new Curtain(MainActivity.this)
                .with(findViewById(R.id.imageView))
                //自定义某个view的高亮形状
                .withShape(findViewById(R.id.btn_shape_custom), new RoundShape(12))
                //是否允许回退关闭蒙层
                .setCancelBackPressed(false)
                // 设置蒙层背景颜色
                .setCurtainColor(0x88000000)
                // 设置蒙层出现的动画 默认渐隐
                .setAnimationStyle(R.style.testAnimation)
                .show();
    }
```

![image](https://upload-images.jianshu.io/upload_images/11595074-e0a033aac3dd8975.gif?imageMogr2/auto-orient/strip)

[Github地址](https://github.com/soulqw/Curtain)