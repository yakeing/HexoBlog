---
title: AMD：RX 6000支持所有光追游戏 私有API的除外
date: 2020-11-09T11:50:02+08:00
tags:
  - AMD
categories:
  - 计算机
abbrlink:
---

AMD RX 6000系列终于支持光线追踪了，但是不同于NVIDIA RTX 20/30系列将光追作为核心卖点大力宣传，AMD这边低调得多，没有吹嘘效果多好，连技术细节也暂未公布。尤其是，RX 6000系列能支持哪些光追游戏呢？

　　AMD今天在一份简短说明中确认，RX 6000系列支持一切使用业界标准技术的光追游戏，包括微软DXR API，以及即将到来的Vulkan光追API，但是使用私有光追API极其扩展的，无法支持。

　　也就是说，《控制》这样的光追游戏，将不再是NVIDIA专属，AMD同样能跑，但是《雷神之锤II RTX》、《德军总部：新血脉》这样和NVIDIA合作密切的光追游戏，AMD就难以触及了，也几乎不可能将它们拉回来。

![img](https://cdn.jsdelivr.net/gh/yakeing/Documentation@main/Hexo/images/7bd2-kcieywa1469928.jpg)

　　这也符合AMD一贯的策略，即坚持遵循开放的行业标准规范，而不是闭门自己搞一套，当然这也是因为AMD实力相对较弱，没有足够的号召力单独拉一套生态，做不出NVIDIA CUDA那样的成就，但也避免了NVIDIA Physx那样的悲剧。

　　从目前了解到的情况看，AMD RDNA 2架构的每个计算单元内都有一个光线加速器（RA），负责光追硬件加速。

　　AMD曾经表态，不会做纯硬件的光追方案，而是软硬件结合，这意味着很多时候性能可能会相对较差一些，但好处是更加灵活，更能战未来。