---
layout:     post
title:      浅谈Switch游戏网络加速（通用）
subtitle:   简单的几种方式，增加你的国外游戏体验！
date:       2019-05-25
author:     NEVER_Gargoyle
header-img: img/post-bg-2015.jpg
catalog: true
tags:
    - SWITCH
    - GAME
    - NSFW
    - BOA
---

一部分大型游戏由国外开发并提供服务，在中国大陆内直接连接服务器有一定困难，尤其是对于联机游戏，这会导致游戏体验大幅下降。这里以switch为例说明几种方法来解决这个问题。

# 方法简介
## 1.使用加速器  
网上有很多供应商的加速器，付费与免费的都有，图方便的就直接用这个吧。  
腾讯将代理任天堂发布switch国行，所以对switch的支持也大了很多。  
目前`腾讯加速器`是主机游戏免费，涵盖美服、日服、港服，效果也还是可观的，不想花钱的可以试一试。（但它背景是免费的，效果不会那么好）  

## 2.修改DNS或Hosts  
这也是一种比较大众的方法，但缺点是这两个东西不太稳定，而且并不是所有游戏通用的。并且要找到一个好用的DNS或Hosts非常难。  
具体操作和我搜集的DNS在下面。  

## *3.使用手机热点（仅适应于switch下载）  
这是一个小技巧，如果你流量充足并且忍不了switch的下载速度的话，可以试一试开热点用流量下载。

## 4.使用境外服务器加速网络连接  
*请注意当地法律法规  
这种方法需要一定的技术（但是我会一步一步的教），也相对来说比较稳定（除了GFW的问题）。最重要的是，它的控制器全部掌握在你的手中，完全不用担心隐私问题，并且相对来说较为便宜。
这篇文章讲重点着手布置一台游戏加速服务器。

# 推荐的加速器  

- [腾讯加速器](https://jiasu.qq.com/)

# DNS  

请注意，DNS有很大的不稳定性，运行商和地区不同效果不同，如果一个用不了请多试几个。  
(我是湖南电信，各个省份并不一样，以下均以美服测试）  

- **1.2.4.8**  
实测！！这个真的有用，虽然速度不是非常快，但是已经好了很多，甚至可以直连warflame。  

- 223.5.5.5  
- 223.6.6.6  

无污染DNS地址： 
- 123.207.22.79   
- 123.207.252.208  
- 202.141.162.123  
USTC无污染DNS地址,支持UDP/TCP 支持5353端口  

- 40.73.101.101  
hixns DNS地址,支持UDP/TCP

# 如何布置一台游戏加速服务器✔️  

1. 购买服务器  
这个环节有很多选择，如果你只是用于加速网络并且要求价格便宜，可以试试这个。
[【微基主机服务-注册地址-支持支付宝、微信】](https://idc.wiki/aff.php?aff=187)  
![image](https://user-images.githubusercontent.com/40263799/58707939-e8a09480-83e8-11e9-9c92-601ba11b7b05.png)  
一年一百左右已经是非常低的价格了，但这类vps性能非常差，只适合用于加速，如何有其它需求请考虑[【Vultr-支持支付宝】](https://www.vultr.com/?ref=7475348)  
注册之后按程序买就好了，创建系统时请选择CentOS,本教程以CentOS系统为准。

2. 连接到服务器  
购买到服务器后，就可以使用了。  
如果连服务器都不会的话，[可以参考这篇百度经验。](https://jingyan.baidu.com/article/3aed632e2b68da70108091d2.html)  
- 下载SSH工具  
我用的是FinalShell，当然其它的都是一样的。[点击这里下载安装包](http://www.hostbuf.com/downloads/finalshell_install.exe)  
安装打开之后基本上是这样的。  
![image](https://user-images.githubusercontent.com/40263799/58745162-d160b600-847f-11e9-823f-876d9926efed.png)  

- 连接服务器  
点击左上方文件夹图标，再点击白底加号图标，选择SSH连接。
![image](https://user-images.githubusercontent.com/40263799/58745190-51871b80-8480-11e9-8ed3-b94c34df819a.png)
![image](https://user-images.githubusercontent.com/40263799/58745196-6ebbea00-8480-11e9-9f24-473ec8f68ace.png)

- 输入服务器IP与用户名密码，完成后双击开始连接  
如果是微基主机的话，首次使用要更改SSH端口，第二次连接时点击名称后方的设置图标改一下就好了。  

3. 原理介绍  
之所以游戏网络很慢，是因为该游戏/服务在中国大陆没有服务器，而中国的海外通道很慢，所以我们要用自己的服务器作为一个中继器，达到提高网速的效果。市面上大部分网络加速都是这个原理。

4. 服务端程序安装  
这里只有复制粘贴进去回车执行就行了。（要一条一条执行）  
>> yum install -y wget  
>安装必要程序  
>> wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocksR.sh  
> 下载sh文件    
>> chmod +x shadowsocksR.sh  
> 给sh文件权限  
>> ./shadowsocksR.sh 2>&1 | tee shadowsocksR.log  
> 运行该文件   


接下来需要配置软件。  
- 设置密码  
![image](https://user-images.githubusercontent.com/40263799/58745454-d4f63c00-8483-11e9-9ae6-0c962cf6c2f5.png)

- 设置服务器端口  
推荐80端口  
![image](https://user-images.githubusercontent.com/40263799/58745465-f48d6480-8483-11e9-87ff-e3e8707a49b4.png)

>> 80

- 选择加密方式  
推荐chacha20,即12
![image](https://user-images.githubusercontent.com/40263799/58745486-3e764a80-8484-11e9-845a-09eb59442501.png)

>> 12

- 选择协议  
推荐auth_sha1_v4,即3  
![image](https://user-images.githubusercontent.com/40263799/58745527-a88eef80-8484-11e9-9a3a-8b76fb8cc733.png)

>> 3

- 选择混淆  
这个选项对服务器的稳定性有较大影响，如果没有非常深入的研究，建议不进行混淆，即1；也可以使用tls1.2_ticket_auth，即6  
其它选项千万不要乱用！  
![image](https://user-images.githubusercontent.com/40263799/58745551-d116e980-8484-11e9-8f6a-6b05ab90ab16.png)

>> 1

- 按任意键继续  
安装过程可能会要一会儿，最后将会用红底显示出你选择过的配置信息，**一定要复制下来或者牢记！！**  

5. 使用端配置  
[基础使用方法参考这篇文章](https://www.jianshu.com/p/c5582a496a3f)  

如果是主机用户，请继续看下去：  
 
**右键飞机图标，进入选项设置**，会弹出如下界面。**勾选"允许来自局域网的连接"**  
![image](https://user-images.githubusercontent.com/40263799/58745751-6a46ff80-8487-11e9-8dc9-86ad5e67072a.png) 
![image](https://user-images.githubusercontent.com/40263799/58745758-85b20a80-8487-11e9-96fb-85d05388b1db.png)  
**win+R打开运行，输入CMD后回车，在弹出的窗口输入ipconfig**  
**找到IPv4地址，记下这串数字。**  

现在可以把电脑开着放在一边了。

5. 在主机端设置  
使主机与电脑连接同一WIFI，打开“网络设置”（应该都有），找到并打开“代理”，将记下的IP地址填进去，端口默认是1080.

6. 享受游戏吧！

