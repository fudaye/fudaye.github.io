---
layout: post
title: Android 基础知识(不断完善)
category: Android 学习笔记
keywords: android,基础
---

## 基本布局
1.FramLayout 
最简单的布局，默认出现在视图的左上角。
2.LinearLayout
最常用的布局之一。一列或者一行显示。控件不能重复叠加。
3.AbsoluteLayout
绝对布局，由于适配的问题，这个布局已经被弃用。
4.RelativeLayout
最常用的布局之一，可以布局视图中空间的相对位置。减少布局的层级，从而减低性能的消耗。
5.TableLayout
我个人不常用。把控件分布在一个表格中，子控件需要根据 TableRow 来控制行的显示。
## Activity 生命周期
![activity 生命周期](http://ooa8w19mz.bkt.clouddn.com/activity%20%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.png)
## Activity LaunchMode
- standard    默认的启动模式，每次创建activity 都在最堆栈中添加一个。
- singleInstance 单独存在在一个任务栈中，后续重复请求都不会重新创建activity，而是调用onNewIntent()方法。再singleInstance 这个栈中只会存在一个实例，而且通过这个实例启动的activity会在主栈中显示。
![流程图](http://ooa8w19mz.bkt.clouddn.com/activity-launch.png)
- singleTop  如果实例存在在栈顶，则不创建，调用onNewIntent()。如果不在栈顶则创建实例。例如微信的地区选择大概就是用的这种启动模式。
- singleTask 栈中只有一个实例，如果存在则会在栈顶显示并且清除再他之上的所有activity，调用onNewIntent()方法，不存在则创建。

## Fragment 生命周期
![Fragment 生命周期](http://ooa8w19mz.bkt.clouddn.com/fragment%20%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.png)

## onSaveInstanceState的调用时机，用于缓存Activity 数据。
- 当用户按下home键
- 锁屏
- 启动了另一个activity
- 横竖屏切换的时候
需要注意的地方：
1.布局中的每一个View默认实现了onSaveInstanceState()方法，这样的话，这个UI的任何改变都会自动地存储和在activity重新创建的时候自动地恢复。但是这种情况只有在你为这个UI提供了唯一的ID之后才起作用，如果没有提供ID，app将不会存储它的状态。
2.不要再onSaveInstanceState()方法中保存持久化数据，因为它是一个瞬间的状态。应该再onPause()方法中保存
3.onSaveInstanceState()如果被调用，这个方法会在onStop()前被触发，但系统并不保证是否在onPause()之前或者之后触发。
## Intent
 Intent 可以传递任何数据，需要实现Parcelable 和 Serializable 接口.Parcelable 接口效率更高。基本数据类型和基本数据类型数组可直接传递。
## Service
- Service 两中启动模式。
1.一种bindService与context绑定，context生命结束，Service生命结束。
2.通过startService 启动 ，此时Service的生命周期与启动它的context无关。需要注意的是需要再AndroidManifest.xml文件中进行注册：
```
 <service
        android:name=".packnameName.youServiceName"
        android:enabled="true" />
```
- 增加Service存活几率
1.再onDestory()方法中从新启动service
2.监听系统广播，判断自己的service是否存在。
## Broadcast Receiver
- 静态注册：在AndroidManifest.xml文件中进行注册，当App退出后，Receiver仍然可以接收到广播并且进行相应的处理
- 动态注册：在代码中动态注册，当App退出后，也就没办法再接受广播了
## ContentProvider
提供不同进程间通信的接口。后续给出示例
## Android 动画类型
- tween 补间动画  使View位移，旋转。 Alpha Scale Translate Rotate。
- Frame 帧动画 AnimationDrawable 控制 animation-list xml布局
- propertyAnimation 属性动画。 实质上控制view移动的动画。而且可以加入插值器，控制动画运动的速率。
## Android 数据保存形式
- File 文件：即常说的文件（I/O）存储方法，常用语存储大数量的数据，但是缺点是更新数据将是一件困难的事情。
- ContentProvider ：Android系统中能实现所有应用程序共享的一种数据存储方式，由于数据通常在各应用间的是互相私密的，所以此存储方式较少使用，但是其又是必不可少的一种存储方式。例如音频，视频，图片和通讯录，一般都可以采用此种方式进行存储。每个Content Provider都会对外提供一个公共的URI（包装成Uri对象），如果应用程序有数据需要共享时，就需要使用Content Provider为这些数据定义一个URI，然后其他的应用程序就通过Content Provider传入这个URI来对数据进行操作。
- SQLite：SQLite是一个轻量级的数据库，支持基本的SQL语法，是常被采用的一种数据存储方式。 Android为此数据库提供了一个名为SQLiteDatabase的类，封装了一些操作数据库的api
- SP（SharedPreference）   除SQLite数据库外，另一种常用的数据存储方式，其本质就是一个xml文件，常用于存储较简单的参数设置。 
## Json 优势
1.易读性
2.高性能解析
3.多语言
4.解析Json的框架丰富
## 怎样退出终止App
首先我对这个问题很费解，再我用过的任何app中没有一个入口是“退出App”。另一个角度退出app就是栈中没有activity。不用集合保存你每次创建的activity 。也不用system.exit(0)。一点也不高大上。我能想到一个简单方法。就是在MainActivity的onNewIntent 方法中监听一个标识比如“exit”。在退出的时候加上一个flag CLEAR_TOP.然后再finish掉MianActivity。

## IntentService的使用场景与特点。

IntentService是Service的子类，是一个异步的，会自动停止的服务，很好解决了传统的Service中处理完耗时操作忘记停止并销毁Service的问题
优点：
- 一方面不需要自己去new Thread
- 另一方面不需要考虑在什么时候关闭该Service 
onStartCommand中回调了onStart，onStart中通过mServiceHandler发送消息到该handler的handleMessage中去。最后handleMessage中回调onHandleIntent(intent)。
## Android长连接，怎么处理心跳机制
## View树绘制流程
## 下拉刷新实现原理
