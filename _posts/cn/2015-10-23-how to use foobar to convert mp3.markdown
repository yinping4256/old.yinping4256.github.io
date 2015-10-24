---
layout: post
title: "利用foobar将无损转mp3/aac教程"
excerpt:
modified:
categories: cn
excerpt:
tags: []
comments: true
image:
  feature: 
  credit: 
  creditlink:
date: 2015-10-23T14:20:33-07:00
---

{% include _toc.html %}

我在[私人云音乐库：网易云音乐还是Groove]({{ site.url }}/cn/private%20music%20cloud/){:target="_blank"}谈到要打造自己的私人音乐库。受于云空间大小的限制、移动端减少流量消耗考虑，我们最好先把无损音乐转为音质较好的mp3或者AAC文件存储在云端。

本文主要介绍在拥有无损音乐格式文件后，如何通过foobar将其转为特定比特率的mp3/aac文件。
至于无损转有损选择多少比特率，可以参考我的这篇文章[音质与大小的权衡:不同比特率比较]({{ site.url }}/cn/mp3%20kbps%20comparison/){:target="_blank"}.

### 安装Foobar

访问Foobar官网下载最新稳定版，完成安装：

<https://www.foobar2000.org/download>{:target="_blank"}
{: .notice}

### APE格式插件

如果无损音乐格式是.ape,则Foobar需要一个插件：Monkey's Audio Decoder。
在安装好Foobar之后下载此插件，双击打开安装即可：

<http://www.foobar2000.org/components/view/foo_input_monkey>
{: .notice}

播放Flac格式无需额外插件。

如果双击.cue文件双击后Foobar无法播放对应的.ape, 则可能是.cue文件标题等出错，用记事本或其他文本编辑器打开后对照.pe文件的文件名看有无出入。

### 下载lame的mp3编码器

lame是mp3格式的编码器中较好的一款，同样比特率下文件更小音质更好。Foobar不内置lame编码器，但是可以在转换的时候指定lame.exe工作。下载地址：

<http://lame.sourceforge.net/download.php>
{: .notice}

下载后解压到任意地方，之后Foobar要调用里面的lame.exe。为了方便我就解压在Foobar的安装目录下了。

如果想转为aac格式(.m4a)，则itunes的aac编码器是比较好的。需要安装一个免费的encoder pack：

<https://www.foobar2000.org/encoderpack>
{: .notice}

显然win下使用itunes的aac编码器需要电脑上已经安装了itunes。

### 确保文件是真无损

这一步其实也很重要。网上有些地方下载的ape,flac文件并不是真无损文件，而是通过mp3转格式转成的。

如何辨别文件是否为真无损，这篇文章写的很详细

<http://wx.shenchuang.com/article/2015-03-11/348893.html>
{: .notice}

简而言之，用GoldWave软件看声谱图。

真无损音乐能轻松超过21kHz，甚至达到22kHz。而320kbps的歌曲，会在20kHz出现明显的切断痕迹。而更低比特率，128kbps会在16kHz左右直接切断。

### 转换格式

直接在foobar播放列表中找到目标歌曲(可以全选)，右键 -> convert -> Quick Convert. 

选好目标格式（比如lame），比特率（比如175kbps), 输出文件的位置(比如source location). 确认无误后点Convert。

第一次运行的时候会弹出界面要你提供lame.exe，找到自己刚刚解压的地方就行了。








