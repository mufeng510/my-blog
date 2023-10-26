---
title: Review Manager 5.4软件汉化
tags: []
date: 2023-10-26 20:07:11
draft: true
hideInList: false
isTop: false
feature: 
---
**RevMan简介**

Review Manager（简称RevMan）是由国际Cochrane协作网为系统评价（systematic review）工作者所提供的专用软件，主要用来制作和保存Cochrane系统评价的计划书或全文，对录入的数据进行Meta分析，并且将Meta分析的结果以森林图等比较直观的形式进行展示，以及对系统评价进行更新。

## 前言

女朋友写论文用到了这个软件，再网上找了一圈没有找到，只找到了一个汉化方法如下：

```
1、在revman5的安装目录中有个rm5.jar文件，c:\program files\review manager5.3

2、我们可以用winrar解压到一个文件夹(比如叫rm5)，

3、然后找到其中的org\cochrane\revman5\resource文件夹，发现有两个文件：text_da.properties和text_en_gb.properties，

第一个是丹麦语言文件，第二个是英语语言文件。

4、我们需要的就是建立一个中文语言文件，这个可以从text_en_gb.properties进行转换，也就是我前述的工作，将其中的菜单及运行中的英文提示进行汉化。

我们可以用ultraedit来对这个文件进行编辑。

完成汉化后的文件保存为text_zh_cn.properties，注意这个文件必须是unicode格式的，如果没有进行格式转换，则菜单会显示为乱码。

ultraedit可以完成格式转换的工作。

得到text_zh_cn.properties文件后，

resource文件夹里面就有三个语言文件了，

其实我们也完全可以把那个丹麦语言文件删除，只保留中文和英文两种。

接下来的工作就是重新生成rm5.jar文件，这个也很容易，将所有文件用winrar压缩成zip格式，得到rm5.zip文件，然后改名为rm5.jar，覆盖到原来的文件夹。这样大功就告成了。

重新启动revman5，然后进入tools-preferences，在interface标签中对preferred language进行设置，选择chinese(china)，保存后重启revman5，已经是中文界面了。
```

并不复杂，最麻烦得还是翻译中文再转成Unicode，不过好在我们现在有了 `ChatGPT` ，整个过程简单了不少，我会把汉化过程写在后面。

## 汉化成果

先上成果：RevMan5.4汉化版

使用方法：

1. 安装 `RevMan_5_4_windows-x64.exe`
2. 打开软件安装目录，使用压缩软件打开 `rm5.jar` ，进入`\org\cochrane\revman5\resource\` ，将 `text_zh.properties` 文件放在这个目录里面，保存。

现在打开软件，进入 `Tools` -> `Preferences` -> `Interface` 设置语言为中文。

![image](https://image-view.yq59.top:2087/i/2023/10/26/image.png)

![image](https://image-view.yq59.top:2087/i/2023/10/26/image_1.png)

## 汉化过程

整个汉化我是按照上面那个教程来的，