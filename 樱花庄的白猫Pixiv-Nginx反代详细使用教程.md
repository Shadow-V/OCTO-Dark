@[TOC](樱花庄的白猫Pixiv-Nginx反代详细使用教程)

# 前言
开头便要感谢一下提供Nginx反代上Pixiv的大佬 **Mashiro**
（我只心血来潮决定写一篇详细教程，程序不是我写的啦）
==本文为樱花庄的白猫上的Nginx反代上P站的详细教程，你可以先去下文的网站，如有什么不懂或是不想动脑才需看此文章==
[此处为Mashiro的网站Pixiv反代原篇 ](https://2heng.xin/2017/09/19/pixiv/)
还有樱花庄的Pixiv交流群号：628285184（建议先去上面的网站）
# 手把手详细教程
接下来就是详细教程（~~其实本人对Nginx反代的原理一窍不通~~，只是教人教的有些多，无奈之下决定写一篇教程）
[此处反正我看不懂的原理 ](https://digi.ninja/blog/domain_fronting.php)


**注意：本文没有任何原理解释！！！只有安装教程~~~**
==

## Nginx反代安装教程
### 1.进入樱花庄的白猫（qwq）下载（~~我知道这步简直***~~，但还是要写的）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190811220524547.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMDgyMTIx,size_16,color_FFFFFF,t_70)

### 2.打开文件夹，找到名为ca.cer的证书，右键点击安装
![记住！选择本地计算机](https://img-blog.csdnimg.cn/20190811220928101.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMDgyMTIx,size_16,color_FFFFFF,t_70)
### 3.下一步后，选择下面的**将所有证书都放入下列储存**，在浏览中选择**受信任的根证书颁发机构**（**这步是确保证书受信任，防止在浏览器中出现安全提示**）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190811221642610.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMDgyMTIx,size_16,color_FFFFFF,t_70)
最后点击下一步，以及完成
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190811221826105.PNG)
出现这个就说明成功惹。。。

### 4.更换Hosts
找到Pixiv-Nginx-master文件夹中的hosts（~~这肯定没问题~~）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190811222457402.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMDgyMTIx,size_16,color_FFFFFF,t_70)
再根据以下路径

C:\Windows\System32\drivers\etc
==
寻找到电脑本地的hosts
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190811222838810.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMDgyMTIx,size_16,color_FFFFFF,t_70)
最后用Pixiv-Nginx-master的hosts覆盖etc文件夹的
完成hosts更改
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190811223032187.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMDgyMTIx,size_16,color_FFFFFF,t_70)
### 5.启动Nginx
找到Pixiv-Nginx-master的可视化工具
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190811223206402.PNG)
打开
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190811223301842.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMDgyMTIx,size_16,color_FFFFFF,t_70)
点击第一个Nginx的Start，Running下的**×**会变成**√**（如果一闪就变回**×**，参考下文**Nginx反代安装中的问题**）
至此，就可以愉快地访问Pixiv惹
### N.最后提醒
由于百度搜索到的Pixiv网址有点问题，Nginx代理可能无法访问，如下
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190811223735299.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMDgyMTIx,size_16,color_FFFFFF,t_70)
就上图这个网址
所以要直接输入    https://www.pixiv.net    （点击也是可以滴）
## Nginx反代安装中的问题


## 夹带的私货——只改Hosts
