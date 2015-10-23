---
layout: post
title: "音质与大小的权衡:不同比特率"
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
date: 2015-10-22T14:20:33-07:00
---

{% include _toc.html %}

本文分为两个部分。首先我会比较mp3和aac，看他们在同等文件大小的情况下谁的音质更好，换言之，性价比最高。然后我会讨论如何选择合适的压缩比特率。

---

## mp3还是aac

一直以来听说同样比特率下aac比mp3的音质要高得多，但同时也看到另一些人的说法认为音质差异和编码器有关。有人认为不能用mp3里较差的编码器和aac里较好的编码器(itunes里的qaac)相比较，而应该使用mp3的lame编码器。今天本人秉着科学求是的精神想彻底比较一下aac和mp3的音质差异。

### 准备工作

* GoldWave 软件，用来观察声谱图<https://www.goldwave.com/release.php>{:target="_blank"}

* Foobar，lame、aac encoder包，参考此文: [利用foobar将无损转mp3/aac教程]({{ site.url }}/how%20to%20use%20foobar%20to%20convert%20mp3/){:target="_blank"}

* 一个无损音频文件：我选择的是李宗盛的"山丘"。链接：http://pan.baidu.com/s/1bnjtIft 密码：numl

需要说明的是，最新的lame版本3.99.5是2012年2月28日更新的(<http://sourceforge.net/projects/lame/files/lame/3.99/>{:target="_blank"})；而qaac最新版2.55是2015年9月23日更新(<http://www.videohelp.com/software/qaac>{:target="_blank"}). 基本上预测qaac会好于lame。

### 经过

我将无损的“山丘”用lame3.99.5压制成4个参数分别为130 kbps VBR, 165 kbps VBR, 225 kbps VBR和320 kbps CBR的文件。

用qaac2.55压制成参数分别为128 kbps VBR, 160 kbps VBR, 224 kbps VBR 和 320 kbps CBR 的四个文件。

以上所提比特率参数均为Convert时提供的默认参数配置。我尽量选择了默认参数较为接近的四组。需要说明的是，用默认VBR参数压制后的文件实际比特率并不一定等于参数提供的标称比特率。

将上面操作得到的8个文件和无损文件，一共9个，分别放到GoldWave里观察声谱图。

在9个文件分别播放到2:43处时，截图声谱图。全部收集好之后比较声谱图的最高可达频率，作为音质的反映。

同时还要比较四组文件的大小。

最后空间性价比由“最高可达频率/文件大小”决定。

### 数据

#### 最高可达频率

<figure class="half">
  <a href="http://{{ site.url }}/images/kbps/130lame.JPG"><img src="http://{{ site.url }}/images/kbps/130lame.JPG"></a>
  <a href="http://{{ site.url }}/images/kbps/128aac.JPG"><img src="http://{{ site.url }}/images/kbps/128aac.JPG"></a>
  <figcaption>130lame vs 128aac</figcaption>
</figure>

<figure class="half">
  <a href="http://{{ site.url }}/images/kbps/130lame.JPG"><img src="http://{{ site.url }}/images/kbps/130lame.JPG"></a>
  <a href="http://{{ site.url }}/images/kbps/128aac.JPG"><img src="http://{{ site.url }}/images/kbps/128aac.JPG"></a>
  <figcaption>165lame vs 160aac</figcaption>
</figure>

<figure class="half">
  <a href="http://{{ site.url }}/images/kbps/130lame.JPG"><img src="http://{{ site.url }}/images/kbps/130lame.JPG"></a>
  <a href="http://{{ site.url }}/images/kbps/128aac.JPG"><img src="http://{{ site.url }}/images/kbps/128aac.JPG"></a>
  <figcaption>225lame vs 224aac</figcaption>
</figure>

<figure class="half">
  <a href="http://{{ site.url }}/images/kbps/130lame.JPG"><img src="http://{{ site.url }}/images/kbps/130lame.JPG"></a>
  <a href="http://{{ site.url }}/images/kbps/128aac.JPG"><img src="http://{{ site.url }}/images/kbps/128aac.JPG"></a>
  <figcaption>320lame vs 320aac</figcaption>
</figure>

要得到上面这些图，需要在GoldWave默认Window设置里把Control窗口设置为Vertical。再在Control左侧窗口右键，选择spectragram。再右键，选择properties->show axis.

#### 图表

|编码器|标称比特率/kbps|实际比特率/kbps|文件大小/MB|最高可达最高频率|空间性价比|
|:--------:|:-------:|:-------:|:-------:|:-------:|:--------:|
|lame|	130|	125	|6.1|	16.7|	2.74 |
|qaac	|128|	122	|6.05|	18.5|	3.06 |
|----
|lame|	165|	147|	7.15|	17.5|	2.45 |
|qaac	|160	|156	|7.65|	19.2	|2.51 |
|----
|lame|	225	|225|	10.9|	19.5|	1.79 |
|qaac|	224|	224|	10.9|	20.5|	1.88 |
|----
|lame	|320	|320|	15.5|	20.2	|1.30 |
|qaac	|320	|320|	15.6	|21.5|	1.38 |
|----
|无损|	859|	859|	41.6|	21.8|	0.52 |
{: rules="groups"}

<figure>
  <a href="http://{{ site.url }}/images/kbps/1.png"><img src="http://{{ site.url }}/images/kbps/1.png"></a>
  <figcaption>文件大小比较</figcaption>
</figure>

<figure>
  <a href="http://{{ site.url }}/images/kbps/2.png"><img src="http://{{ site.url }}/images/kbps/2.png"></a>
  <figcaption>最高频率比较</figcaption>
</figure>

<figure>
  <a href="http://{{ site.url }}/images/kbps/3.png"><img src="http://{{ site.url }}/images/kbps/3.png"></a>
  <figcaption>空间性价比比较</figcaption>
</figure>

### 结论

同等比特率下，aac确实比mp3音质更好。这在低比特率的时候表现尤其明显。

---

## 压缩比特率的选择

强烈建议大家决定比特率的时候使用ABX测试(<https://en.wikipedia.org/wiki/ABX_test>{:target="_blank"}}，而不要一味追求高音质而选择非常高的比特率。

毕竟，如果自己耳朵都听不出差别的话，就没有必要在移动场合还用特别高的比特率听歌了。

从上面图片中我们可以看到，225kbps的文件就已经超过10MB了。这其实并不十分经济。