---
title: 手机混用闪存到底是真是假？教你查手机闪存型号
date: 2020-11-08T18:25:32+08:00
tags:
  - 闪存
categories:
  - 手机
abbrlink:
---

最近，网上传言某手机混用闪存，将UFS 3.0和UFS 3.1的闪存混用在了同一型号的机器上，买不同容量的手机，闪存协议不一样。光从这个描述来看，这做法相当不厚道，消费者买手机等于抽奖。但这到底是不是真的？很多朋友也只是有所耳闻，但却不知道如何验证。今天，就给大家分享一些方法。

　　方法一：拨号面板输入指令查询

　　这是适用于部分ROM的方法，例如某些版本的MIUI、EMUI等ROM就可以使用。在拨号界面中，输入“*#*#284#*#*”，系统就会开始生成Debug报告，等待Debug报告生成完毕，整个过程应该不到一分钟。

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/04c4-kcpxnwv7039431.jpg)

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/75e4-kcpxnwv7039432.jpg)

　　输入*#*#284#*#*

　　这个Debug报告包含很多文件，以MIUI为例，这些文件处于手机内部存储的“MIUI\debug_log”目录下。开启这个目录，找到“bugreport-日期时间”文件名格式的zip包，开启这个zip包。

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/af44-kcpxnwv7039500.png)

　　MIUI中的Debug报告

　　在这个zip包当中，还包含着另一个zip包，它的文件名是“bugreport-设备名-安卓版本-日期时间”。

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/6832-kcpxnwv7039501.png)

　　其中的bugreport压缩包

　　打开这个zip包，里面有一个和这个zip包同名的txt文件，开启即可。

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/c014-kcpxnwv7039532.png)

　　开启这个txt文件

　　这个txt文件中，搜索“ffu”的字串，很容易就可以找到闪存型号的信息。例如笔者手中的这部手机，它的闪存型号是“KLUCG4J1ED-B0C1”，制造商是三星。

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/f610-kcpxnwv7039533.png)

　　其中可以找到闪存具体型号

　　方法二：系统Bugreport查询

　　这个方法适用于大部分的安卓手机。首先，需要开启安卓机的开发者选项，在设置菜单的系统信息界面，不断点击“版本号”即可开启。

　　接着，设置界面就多了“开发者模式”的选项，这个选项通常位于“系统”下。进入开发者选项，可以看到“错误报告”的功能，点击后，选择生成报告。

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/30c3-kcpxnwv7039550.jpg)

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/81be-kcpxnwv7039551.jpg)

　　开发者模式下生成bugreport

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/0e1a-kcpxnwv7039555.jpg)

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/d987-kcpxnwv7039556.jpg)

将bugreport保存到存储空间，或者发送到其他地方

　　等待一段时间后，系统通知栏就会弹出“已获取错误报告”的信息。点开它，看到了警告信息后，将它保存到系统目录当中。错误报告是一个文件名为“bugreport-设备名-安卓版本-日期时间”的zip包

　　接下来的操作就和方法一差不多了。在这个zip包里面，找到同名的txt文件，然后在其中搜索“ffu”，就能找到闪存型号。

　　但也要注意，现在某些厂商默认并不将闪存的相关信息写入Bugreport当中，或者是搜索的关键词不同（例如有的手机要搜“ufs_product_name”），这需要大家亲自尝试了。

　　方法三：终端命令行查询

　　安卓系统基于Linux内核，因此想要确认安卓机的一些信息，也可以通过Linux中常用的终端来进行。

　　首先下载安装一个终端App，这类App非常丰富，这里就不特别提供了，大家可以自行搜寻安装。

　　在终端中输入以下命令行：

　　cat/proc/scsi/scsi

　　之后，终端就会呈现出闪存的制造商、具体型号等信息了。

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/c1df-kcpxnwv7039561.png)

　　在终端，输入命令行也可以查看到闪存具体型号

　　不过，这个方法并非什么机器都可以用，某些厂家已经屏蔽了相关信息的调用，就算输入命令也不会返回任何信息，这就看不到闪存型号的信息了。

　　某手机真的混用UFS 3.0和UFS 3.1闪存了吗？

　　找到了闪存型号后，要确认对应规格就很容易了，直接通过搜索引擎，或者制造商的官网查找即可。

　　这次某些朋友是买到了某手机的256G容量的型号，因为闪存跑分略低，被怀疑是UFS 3.0，和宣传的UFS 3.1不符。据了解，对应的闪存型号为“SDINFDK4-256G”，我们就以它为例子，来鉴定一下到底这是什么闪存规格。

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/c23f-kcpxnwv7039562.jpg)

　　网络上受争议的某手机256G版闪存型号

　　从搜索引擎中，很容易就找到了该闪存的官方规格文件，这里把链接也提供给大家。

　　西数/闪迪闪存规格文件：https：//documents.westerndigital.com/content/dam/doc-library/en_us/assets/public/western-digital/product/embedded-flash/brochure/brochure-western-digital-eis-mobile.pdf

　　从文件中，很容易就找到了“SDINFDK4-256G”的对应规格。可见这就是UFS 3.1的闪存，宣传并没有错谬。

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/badd-kcpxnwv7039570.png)

　　其实是货真价实的UFS 3.1

　　至于和128G版本的性能差异，是由于闪存的性能不仅仅和协议有关，NAND也是重要的决定因素——正如同样是PCIe 4.0的SSD，不同型号性能也有高下之分。

　　总结

　　总的来说，作为手机中的重要部件，闪存的确很大程度上决定了手机的体验。如果你对闪存信号有疑惑，不妨试试上文的方法，相信可以帮到大家。