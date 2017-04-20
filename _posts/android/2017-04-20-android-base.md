---
layout: post
title: Android ����֪ʶ(��������)
category: Android ѧϰ�ʼ�
keywords: android,����
---

## ��������
1.FramLayout 
��򵥵Ĳ��֣�Ĭ�ϳ�������ͼ�����Ͻǡ�
2.LinearLayout
��õĲ���֮һ��һ�л���һ����ʾ���ؼ������ظ����ӡ�
3.AbsoluteLayout
���Բ��֣�������������⣬��������Ѿ������á�
4.RelativeLayout
��õĲ���֮һ�����Բ�����ͼ�пռ�����λ�á����ٲ��ֵĲ㼶���Ӷ��������ܵ����ġ�
5.TableLayout
�Ҹ��˲����á��ѿؼ��ֲ���һ������У��ӿؼ���Ҫ���� TableRow �������е���ʾ��
## Activity ��������
![activity ��������](http://ooa8w19mz.bkt.clouddn.com/activity%20%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.png)
## Activity LaunchMode
- standard    Ĭ�ϵ�����ģʽ��ÿ�δ���activity �������ջ�����һ����
- singleInstance ����������һ������ջ�У������ظ����󶼲������´���activity�����ǵ���onNewIntent()��������singleInstance ���ջ��ֻ�����һ��ʵ��������ͨ�����ʵ��������activity������ջ����ʾ��
![����ͼ](http://ooa8w19mz.bkt.clouddn.com/activity-launch.png)
- singleTop  ���ʵ��������ջ�����򲻴���������onNewIntent()���������ջ���򴴽�ʵ��������΢�ŵĵ���ѡ���ž����õ���������ģʽ��
- singleTask ջ��ֻ��һ��ʵ����������������ջ����ʾ�����������֮�ϵ�����activity������onNewIntent()�������������򴴽���

## Fragment ��������
![Fragment ��������](http://ooa8w19mz.bkt.clouddn.com/fragment%20%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.png)

## onSaveInstanceState�ĵ���ʱ�������ڻ���Activity ���ݡ�
- ���û�����home��
- ����
- ��������һ��activity
- �������л���ʱ��
��Ҫע��ĵط���
1.�����е�ÿһ��ViewĬ��ʵ����onSaveInstanceState()�����������Ļ������UI���κθı䶼���Զ��ش洢����activity���´�����ʱ���Զ��ػָ��������������ֻ������Ϊ���UI�ṩ��Ψһ��ID֮��������ã����û���ṩID��app������洢����״̬��
2.��Ҫ��onSaveInstanceState()�����б���־û����ݣ���Ϊ����һ��˲���״̬��Ӧ����onPause()�����б���
3.onSaveInstanceState()��������ã������������onStop()ǰ����������ϵͳ������֤�Ƿ���onPause()֮ǰ����֮�󴥷���
## Intent
 Intent ���Դ����κ����ݣ���Ҫʵ��Parcelable �� Serializable �ӿ�.Parcelable �ӿ�Ч�ʸ��ߡ������������ͺͻ����������������ֱ�Ӵ��ݡ�
## Service
- Service ��������ģʽ��
1.һ��bindService��context�󶨣�context����������Service����������
2.ͨ��startService ���� ����ʱService��������������������context�޹ء���Ҫע�������Ҫ��AndroidManifest.xml�ļ��н���ע�᣺
```
 <service
        android:name=".packnameName.youServiceName"
        android:enabled="true" />
```
- ����Service����
1.��onDestory()�����д�������service
2.����ϵͳ�㲥���ж��Լ���service�Ƿ���ڡ�
## Broadcast Receiver
- ��̬ע�᣺��AndroidManifest.xml�ļ��н���ע�ᣬ��App�˳���Receiver��Ȼ���Խ��յ��㲥���ҽ�����Ӧ�Ĵ���
- ��̬ע�᣺�ڴ����ж�̬ע�ᣬ��App�˳���Ҳ��û�취�ٽ��ܹ㲥��
## ContentProvider
�ṩ��ͬ���̼�ͨ�ŵĽӿڡ���������ʾ��
## Android ��������
- tween ���䶯��  ʹViewλ�ƣ���ת�� Alpha Scale Translate Rotate��
- Frame ֡���� AnimationDrawable ���� animation-list xml����
- propertyAnimation ���Զ����� ʵ���Ͽ���view�ƶ��Ķ��������ҿ��Լ����ֵ�������ƶ����˶������ʡ�
## Android ���ݱ�����ʽ
- File �ļ�������˵���ļ���I/O���洢������������洢�����������ݣ�����ȱ���Ǹ������ݽ���һ�����ѵ����顣
- ContentProvider ��Androidϵͳ����ʵ������Ӧ�ó������һ�����ݴ洢��ʽ����������ͨ���ڸ�Ӧ�ü���ǻ���˽�ܵģ����Դ˴洢��ʽ����ʹ�ã����������Ǳز����ٵ�һ�ִ洢��ʽ��������Ƶ����Ƶ��ͼƬ��ͨѶ¼��һ�㶼���Բ��ô��ַ�ʽ���д洢��ÿ��Content Provider��������ṩһ��������URI����װ��Uri���󣩣����Ӧ�ó�����������Ҫ����ʱ������Ҫʹ��Content ProviderΪ��Щ���ݶ���һ��URI��Ȼ��������Ӧ�ó����ͨ��Content Provider�������URI�������ݽ��в�����
- SQLite��SQLite��һ�������������ݿ⣬֧�ֻ�����SQL�﷨���ǳ������õ�һ�����ݴ洢��ʽ�� AndroidΪ�����ݿ��ṩ��һ����ΪSQLiteDatabase���࣬��װ��һЩ�������ݿ��api
- SP��SharedPreference��   ��SQLite���ݿ��⣬��һ�ֳ��õ����ݴ洢��ʽ���䱾�ʾ���һ��xml�ļ��������ڴ洢�ϼ򵥵Ĳ������á� 
## Json ����
1.�׶���
2.�����ܽ���
3.������
4.����Json�Ŀ�ܷḻ
## �����˳���ֹApp
�����Ҷ��������ܷѽ⣬�����ù����κ�app��û��һ������ǡ��˳�App������һ���Ƕ��˳�app����ջ��û��activity�����ü��ϱ�����ÿ�δ�����activity ��Ҳ����system.exit(0)��һ��Ҳ���ߴ��ϡ������뵽һ���򵥷�����������MainActivity��onNewIntent �����м���һ����ʶ���硰exit�������˳���ʱ�����һ��flag CLEAR_TOP.Ȼ����finish��MianActivity��

## IntentService��ʹ�ó������ص㡣

IntentService��Service�����࣬��һ���첽�ģ����Զ�ֹͣ�ķ��񣬺ܺý���˴�ͳ��Service�д������ʱ��������ֹͣ������Service������
�ŵ㣺
- һ���治��Ҫ�Լ�ȥnew Thread
- ��һ���治��Ҫ������ʲôʱ��رո�Service 
onStartCommand�лص���onStart��onStart��ͨ��mServiceHandler������Ϣ����handler��handleMessage��ȥ�����handleMessage�лص�onHandleIntent(intent)��
## Android�����ӣ���ô������������
## View����������
## ����ˢ��ʵ��ԭ��
