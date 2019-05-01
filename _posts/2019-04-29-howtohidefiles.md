---
layout:     post
title:      多种方法隐藏/加密你的文件
subtitle:   【BOA】总结了网上的大部分方法，在这里总有一个适合的方法。
date:       2019-04-29
author:     NEVER_Gargoyle
header-img: img/post-bg-unix-linux.jpg
catalog: true
tags:
    - PC
    - BOA
    - 技术
---

在各种场景中，总会有很多需要隐藏的文件，我参考了网上的各种加密方法，总结出这篇文章。读者可以参考使用。  

## 1.隐藏文件/文件夹  

### 1.1 使用Windows自带隐藏功能

该方法非常方便，只需要一个右键单击一个左键单击就完成了。但是这个方法非常不安全，基本上是形同虚设，稍微有点电脑知识的人都看得到......所以这个方法最好配合文件加密使用。

加密方法：（以win10为范例）

- 右键要加密的文件/文件夹

![image](https://user-images.githubusercontent.com/40263799/56960043-25773280-6b82-11e9-8e96-0fa548b817e5.png)

- 点击属性

![image](https://user-images.githubusercontent.com/40263799/56960083-3de74d00-6b82-11e9-8dd0-31ae7151b592.png)

- 勾选隐藏

![image](https://user-images.githubusercontent.com/40263799/56960104-4f305980-6b82-11e9-8d97-adb604cd35b1.png)

解密方法：同理，取消勾选隐藏。

### 1.2 使用磁盘管理

这种方法的原理是删除一个磁盘的卷标以隐藏里面的文件。这种方法大部分人不知道如果解密或者不会想到用了这种方法，但是对于有较高计算机水平的人也是形同虚设。

使用方法：

- 右键“我的电脑”  

![image](https://user-images.githubusercontent.com/40263799/56959979-e812a500-6b81-11e9-86e8-b7e408e18abb.png)

- 单击“管理”

![image](https://user-images.githubusercontent.com/40263799/56960133-65d6b080-6b82-11e9-9a7e-024dc1be4b40.png)

- 单击“磁盘管理”

![image](https://user-images.githubusercontent.com/40263799/56960156-79821700-6b82-11e9-8a73-1ad2493179aa.png)

- 初次使用时，请先压缩卷（不要把C盘删了）

![image](https://user-images.githubusercontent.com/40263799/56960175-8bfc5080-6b82-11e9-9a84-39b987cffdd9.png)

- 对需要隐藏的磁盘分区右键

![image](https://user-images.githubusercontent.com/40263799/56960207-a2a2a780-6b82-11e9-8605-a7837496a10b.png)

- 更改驱动器号及路径（主要千万不要格式化了)

![image](https://user-images.githubusercontent.com/40263799/56960251-c1a13980-6b82-11e9-9604-c6db0fafdc38.png)

- 隐藏则删除盘符，解密时添加就行了

![image](https://user-images.githubusercontent.com/40263799/56960336-fe6d3080-6b82-11e9-8b24-acd8b9f38bfe.png)

### 1.3 使用辅助软件  

网上有很多此类软件，但根据大家的反馈都不太理想，要不就是容易破解，要不就是**容易导致文件被删**！所以请谨慎使用。

## 2.加密文件

### 2.1 使用压缩包加密

这个方法用的非常多。就不用我来教了。

### 2.2 通过修改/删除后缀名加密

这种方法比较简单，但是缺点是不同文件的后缀名不一样，一旦忘记就很麻烦。而且一些大佬可以根据.txt的文本看出原来是什么后缀名的文件。

使用方法：

- 重命名

- 删除/修改 ".xxx"

### 2.3 使用辅助软件

这类的辅助软件和隐藏文件的不一样，大多数是非常棒的。大致原理是加密内容生成一个新的文件。
# 未完待续
