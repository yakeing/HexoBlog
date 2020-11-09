---
title: 微软强制退休IE浏览器：部分网址只能用Edge打开
date: 2020-11-08T18:25:32+08:00
tags:
  - 微软
  - 浏览器
categories:
  - 新闻
abbrlink:
---

用喜新厌旧来形容微软的某些产品策略，可能再合适不过了。

　　这一次遭殃的是IE浏览器，曾经帮微软战胜网景，开启互联网巨头征程的功勋软件。

　　据悉，从下月开始，部分URL地址将无法通过IE打开，你需要使用新Edge才行。

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/08ac-kcaeqzx1004768.png)

　　原来，微软密谋上述操作从今年夏天的Edge 84版本就开始了，定于下月上线的Edge 87则准备正式激活该特性。

　　专家研究后发现，特性的激活与名为ie_to_edge_bho.dll的dll文件有关，调用的是Browser Helper Object （BHO）。BNO文件的默认地址是：

　　C：\Program Files\Microsoft\Edge\Application\[VERSION]\BHO\

　　C：\Program Files （x86）\Microsoft\Edge\Application\[VERSION]\BHO\

　　尽管BHO文件藏在Edge目录下，但用户每次试图打开IE时就会在注册表中加载。

　　已经确认受影响的网址包括ESPN、雅虎邮箱、GoDaddy、YouTube、Twitter、Instagram、VK、Chase、StackOverflow、Hotstar、Moneygram、eharmony等。

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/fd12-kcaeqzx1004769.png)