---
layout: post
title: �����ֽ���ͨ��github���Ѳ���
category: ����
tags: [Windows , ����,Jekyll]
description: 
---

### ����
  д���͵ĺô�����˵�ˣ�ϣ����ƪ���¿��԰�������ٴһ�������Լ�����Ѳ��͡�
- github + [3-Jekyll](https://github.com/P233/3-Jekyll)  ��л [Peiwen Lu](https://github.com/P233) ������ôƯ�������⣬��л [suyan](https://github.com/suyan) ����
- �㲻��Ҫ������
- high ������ɧ��

### ���� 
windows    Jekyll     github


### ��һ�� ��һ��github�˺�
ע���ַ��[github](https://github.com/)���������ע�����Ҷ��
### �ڶ��� Fork ��Ŀ���Լ����˺�
��������ַ--> https://github.com/suyan/suyan.github.io
![](http://upload-images.jianshu.io/upload_images/2021109-5d90e36d180949d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
���"Fork",�������ĿFork���Լ����˻��¡�
![](http://upload-images.jianshu.io/upload_images/2021109-e5fb490bf1289f05.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
��Ľ�����Ҫ�޸���������������ʲ��͡������Settings�����޸ĳ�username.github.io ����ʽ��Ȼ��������������� username.github.io �����ַ�Ϳ�����ʾ������������ �ҵ�username ��fudaye ��ô����fudaye.github.io  ����fudaye�� �滻�����Լ���username���ɡ�
��������������ʲ��ͣ���ϲ�����Ѿ��ɹ�һ���ˣ�

###������ ��Ҫ����һ��git��С֪ʶ��
����һ�� [git for windows �ͻ���](http://ooaeymn9o.bkt.clouddn.com/Git-2.8.1-64-bit.exe)��һ·next��
![](http://upload-images.jianshu.io/upload_images/2021109-e7d0fc771387796c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
��ᷢ�ֶ�����ô�����������㿪 git bash�����������  git version, ���鿴��ǰ�汾�š�
![](http://upload-images.jianshu.io/upload_images/2021109-e407f53bc2407fa3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

����������� ��ϲgit�Ѿ��ɹ���װ��
git С֪ʶ������ϸ�˽�git֪ʶ��鿴[��ѩ����ʦ�̳�](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
����ֻ��Ҫ�õ�����������
#### 1.ssh-keygen -t rsa -C "youremail@example.com" ������Կssh��
���һ��˳���Ļ����������û���Ŀ¼���ҵ�.sshĿ¼��������id_rsa��id_rsa.pub�����ļ�������������SSH Key����Կ�ԣ�id_rsa��˽Կ������й¶��ȥ��id_rsa.pub�ǹ�Կ�����Է��ĵظ����κ��ˡ�
#### 2.��½GitHub���򿪡�Account settings������SSH Keys��ҳ��
Ȼ�󣬵㡰Add SSH Key������������Title����Key�ı�����ճ��id_rsa.pub�ļ������ݣ�
![](http://upload-images.jianshu.io/upload_images/2021109-994a4dc5a1b3b240.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
��֤�������ύ�ļ���ʱ�򲻱�����д���룬������ж�����Կ�����Ӷ��key��
#### 3.git clone 
![](http://upload-images.jianshu.io/upload_images/2021109-a896cab9a434393a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
��� use SSH 
```
$ git clone git@github.com:fudaye/fudaye.github.io.git
Cloning into 'gitskills'...
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (3/3), done.
```
C:\Users\acer һ���ڸ��˵������Ŀ¼�»ط����Ѿ�clone��������Ŀ
#### 4.git add [files]
�����޸���Ҳ����������޸��ļ���һ��Ҫʹ������������ύ�����޸ĵ��ļ�
#### 5.git commit -m "������ע��" ������������ύ����ļ���
#### 6.git origin master �����㱾�ؿ����͵�github��
#### 7. git status  ������������鿴״̬��
Ȼ�������Ĳ��;Ϳ��Կ������ģ����л��棩��
### ���Ĳ� ���ø�����Ϣ _config.yml
������������Լ�����������һ����������Ϊ����
1.����clone����Ŀ���ҵ�CNAME����ļ��������޸ĳ����������ַ
2.�ڰ����ƹ�������
3.���ӽ���
![](http://upload-images.jianshu.io/upload_images/2021109-509077ff4133d0ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
ǰ����Ϊ�̶�ip��ַ��������Ϊ���github���͵�ַ��
### ���岽  �Ҹ����Ա༭���ֵĹ��ߣ��Ϳ��Լ�¼������ĵ��ε�����
�ο�_posts�е�Ŀ¼�ṹ�Լ������ʺ��Լ�������Ŀ¼�ṹ���򵥽���һ�£�
�����㽨����һƪ���ͣ����ڸ�ʽ��Ҫ�ı䣬��ߵ����ֿ��Ը��ġ�
2016-11-17-airbnb-boggle-game.md
```
---
layout: post
title: Airbnb Boggle Game
category: ����  (���Ʋ���������������)
tags: Airbnb,Interview
keywords: Airbnb,Interview,Boogle Game
---
```
�����ǹ̶���ʽ��ÿһƪ���ͱ���Ҫ�У�

### ���
�˷�ʥ�������޹����д������λү��ʱ���ѡ�