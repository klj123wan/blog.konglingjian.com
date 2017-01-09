+++
date = "2017-01-09T16:23:13+08:00"
tags = ["charles"]
categories = ["工具"]
title = "使用 Charles 获取 https 的数据"

+++

今天微信小程序上线，研究了一下其他的微信小程序。现在因为苹果必须要支持https，导致现在接口基本都是https了。突然发现使用charles抓取https都是乱码。现在分享一下接口办法。

<!--more-->

我使用的 Charles 版本是 3.10，获取下载地址可自行百度，我下面要说的是使用 Charles 获取 https 的数据。

### 1.配置 Charles 根证书

首先打开 Charles:

![](/img/charles/charles_1.png)
![](/img/charles/charles_2.jpg)

然后如下图操作：

![](/img/charles/charles_3.jpg)

之后会弹出钥匙串，如果不弹出，请自行打开钥匙串，如下图：

![](/img/charles/charles_4.jpg)

系统默认是不信任 Charles 的证书的，此时对证书右键，在弹出的下拉菜单中选择『显示简介』，点击使用此证书时，把使用系统默认改为始终信任，如下图：

![](/img/charles/charles_5.jpg)

然后关闭，就会发现 charles 的证书已经被信任了，如下图：

![](/img/charles/charles_6.jpg)

### 2. 在移动设备上配置证书

如下图，选择在移动设备上安装 Charles 根证书：

![](/img/charles/charles_7.jpg)

会弹出一个提示框，如下图：

![](/img/charles/charles_8.jpg)

然后打开手机的浏览器，输入 
charlesproxy.com/getssl 会弹出如下界面：

![](/img/charles/charles_9.jpg)

点击安装即可。

进入手机设置界面：

![](/img/charles/charles_10.jpg)

这里以简书为例…

![](/img/charles/charles_11.jpg)

此时还是获取不到 https 的数据，各位童鞋不要着急，下面还有操作，接着还是进入 Charles ,如下图操作：

![](/img/charles/charles_12.jpg)

如下图，勾选Enable SSL Proxying,点击添加，弹出下面的对话框，Host 表示你要抓取的 ip 地址或是链接，Port 填写 443 即可：

![](/img/charles/charles_13.jpg)

设置完成后，就可以抓取数据啦，如下图：

![](/img/charles/charles_13.jpg)

如果有问题，欢迎留言。^_^

