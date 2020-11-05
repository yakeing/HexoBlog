---
title: 常用 Markdown 语法
description: Markdown 使用及基本特性
date: 2020-09-17T13:30:00Z
tags:
  - code
categories:
  - Github
abbrlink: k9hdu
---

Markdown 是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档。

Markdown 语言在 2004 由约翰·格鲁伯（John Gruber）创建。

Markdown 编写的文档可以导出 `HTML` 、`Word`、`图像`、`PDF`、`Epub` 等多种格式的文档。

下面看一下效果如何:

标签 `tag` `tag2`

斜体 *斜体字* _斜体字2_

加粗 **加粗字** __加粗字2__

删除 ~~删除线~~

分割摘要（首页看效果）

<!--more-->

> 块引用效果
> 1. 第一项
> * 第二项
> > 第二层嵌套
> > > 第三层嵌套

要注明的文本脚注 [^RUNOOB]

[^RUNOOB]: 显示注明文字

--- 换行 ---

定义一行(后面加两个空格换行)
换行了

--- 链接 ---

[Blog](https://yake.tk)

--- 图片 ---

![Yakeing](https://avatars2.githubusercontent.com/u/6356091?s=200&v=4 'Yakeing')

--- 数组列表 ---

1. 一列
2. 二列
3. 三列
   1. 三列1
   2. 三列2
   3. 三列3

--- 无序列表 ---

* 星号(*)
+ 加号(+)
- 减号(-)

或者

- 一级列表
- 如果您有子列表，请在破折号或星号前放置两个空格:
  - 二级列表
  - 二级列表

--- 标题效果 ---

# h1效果 （===）

## h2效果（- - -）

### h3效果

#### h4效果

##### h5效果

###### h6效果

--- 分割线（***） ---

***

--- 表格效果 ---

| icon | id | class name | glyph name |
| :----: | :----: | :---- | :---- |
| <i class="icon-paste vm"></i> | f0ea | icon-paste | clipboard, paste |
| <i class="icon-creative-commons vm"></i> | f25e | icon-creative-commons | creative-commons |
| <i class="icon-arrow-double-down vm"></i> | f103 | icon-arrow-double-down | angle-double-down |
| <i class="icon-arrdouble-left vm"></i> | f100 | icon-arrdouble-left | angle-double-left |
| <i class="icon-arrow-double-right vm"></i> | f101 | icon-arrow-double-right | angle-double-right |
| <i class="icon-arrow-double-up vm"></i> | f102 | icon-arrow-double-up | angle-double-up |
| <i class="icon-arrow-down vm"></i> | f107 | icon-arrow-down | angle-down |

--- 复选框效果 ---

- [x] 被选中
- [ ] 没选中

--- 语法高亮 ---

```javascript
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```
代码区块使用 4 个空格或者一个制表符(Tab 键)

--- Emoji表情 ---

显示效果参考：https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md

--- 画图 ---

当然还有 `typora`、`画流程图`、`时序图(顺序图)`、`甘特图` 等等...
