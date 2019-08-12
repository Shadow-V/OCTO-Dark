@[TOC](樱花庄的白猫Pixiv-Nginx反代详细使用教程)

# 前言
开头便要感谢一下提供Nginx反代上Pixiv的大佬 **Mashiro**
（我只心血来潮决定写一篇详细教程，程序不是我写的啦）
==本文为樱花庄的白猫上的Nginx反代上P站的详细教程，你可以先去下文的网站，如有什么不懂或是不想动脑才需看此文章==
https://2heng.xin/2017/09/19/pixiv/
# 手把手详细教程
接下来就是详细教程（~~其实本人对Nginx反代的原理一窍不通~~，只是教人教的有些多，无奈之下决定写一篇教程）
[此处反正我看不懂的原理 ](https://digi.ninja/blog/domain_fronting.php)


==注意：本文没有任何原理解释！！！只有安装教程==
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
### 1.浏览器出现您的连接不是私密连接
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190812090426295.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMDgyMTIx,size_16,color_FFFFFF,t_70)
你可以通过点击高级来继续访问，但仍有可能出现问题
所以最好参考上文第3步的证书安装
[这里是大佬Mashiro的处理方法](https://github.com/mashirozx/Pixiv-Nginx/wiki/“您的链接不是私密链接”排查方法)
### 2.可视化工具无法打开
可会出现因Framework的缺少导致以下的问题
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190812130036266.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMDgyMTIx,size_16,color_FFFFFF,t_70)
[去官网下一个就行惹](https://docs.microsoft.com/zh-cn/dotnet/framework/install/on-windows-7)
### 3.报错解析
有可能你会发现，Nginx的√一闪就回到**×**，这时你要打开Pixiv-Nginx-master里的logs文件夹，找到error.log，里面会有错误信息。
以下为解析（~~我也不知道对不对的那种，参考参考~~）
1.conflicting server name "hlsa6.pixivsketch.net" on....
这是由于大佬Mashiro的疏忽导致，目前只存在于老版本，下载新版即可
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190812091617378.png)
2.CreateFile()"安装路径" failed(1113:No mapping for the Unicode character exists in....)
安装路径带有中文
安装路径全英文即可消除错误
3.build() to 0.0.0.0.80 failed(10013 : An attempt was made to access a socket in a way...)
端口占用，用cmd找一下占用80端口的软件，关掉(其实不一定是80，这个要自己看）
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019081212591713.png)

如果你想两个共存
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190812125311619.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMDgyMTIx,size_16,color_FFFFFF,t_70)
在这个文件里更改端口
listen 后面那个数字哦
## 只改Hosts
这个嘛，就是不通过反代，直接靠IP地址上Pixiv
只需靠上文的改hosts那一段就行了
[这是我手头上的一个，有一堆诸如Google、Wiki、YouTube之类的，但亲测只有Pixiv有效](https://pan.baidu.com/s/1HQpGPwALgKVRBYj8mdleKw)
提取码: 73n3
参照上文更换hosts即可
# 其他
其他倒是没啥
Andorid系统可通过VPN上Pixiv
当然樱花庄上也有、
方法我倒是没试过，也是安装证书，修改hosts，我苹果手机T T（~~老老实实用VPN吧~~）
其实苹果也是可以的，不过要越狱
[iOS详情](https://github.com/mashirozx/Pixiv-Nginx/wiki/iOS-修改-hosts-的方法)
# 写在最后
其实这个教程，实在是太过于详细，其实你本来靠樱花庄上的文章就能实现
但是嘛，总会出些问题（~~或者是你懒，不想想~~）
~~你要是看了这篇还是不会。。。我也没办法~~
