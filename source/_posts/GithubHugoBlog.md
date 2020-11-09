---
title: 使用hugo+Github博客搭建教程
date: 2020-09-02T17:20:00Z
tags:
  - Blog
  - Hugo
categories:
  - Github
abbrlink: k92hk
---

### 什么是hugo

Hugo是由Go语言实现的静态网站生成器。简单、易用、高效、易扩展、快速部署。对比Hexo，Hugo仅需一个二进制文件（hugo.exe）即可实现网站生成的生成。而且就如它官网介绍：`The world’s fastest framework for building websites`。Hugo是目前最快的网站构建框架。凭借其惊人的速度和灵活性，解决了环境依赖、性能较差的问题，还有使用简单、部署方便等诸多优点，通过 `LiveReload` 实时刷新，极大的优化文章的写作体验。Hugo使建站再次变得有趣。

### hugo能做什么

hugo是静态网站生成器，能够作为一些展示类网站的解决方案。比如个人博客、产品介绍、个人作品展示、文档介绍、公司官网等等。再加上`Github Pages`的功能，就能不花一分钱建一个自己的网站了。

<!--more-->

# 开始使用hugo
---
### 下载安装hugo

我们为了简便快速当然选择hugo的二进制安装方式，源码安装有机会再去学习。

去hugo的官方 [Github仓库](https://Github.com/gohugoio/hugo/releases) 下载对应的操作系统版本的Hugo二进制文件:

```txt
    hugo_*.**.*_Windows-32bit.zip   12.7 MB (系统是32位)
    hugo_*.**.*_Windows-64bit.zip   13.8 MB (系统是64位)
```

注意: `*号是版本号`

博主以`windows64`位操作系统为例，下载对应的Windows-64bit.zip，下载完成后解压缩得到文件。

```txt
    hugo.exe    22.67 MB
    LICENSE     0.01 MB
    README.md   0.01 MB
```

苹果 `Mac` 下直接使用`Homebrew`安装：(其他步骤同理略)

```shell
    brew install hugo
```

### hugo环境变量配置

上一步操作，可以看到我们把`hugo.exe`解压到了`D:\hugo`下面。所以`hugo`命令只能在该目录下才能识别。但是我们想要把博客目录建到其他目录下，这就需要配置环境变量。

```txt
    此电脑->右键->点击属性->再点击高级系统设置->点击环境变量->在系统变量中找到path->再点击编辑
```

点击新建，填入`hugo`解压的文件目录，比如博主解压在 `D:\hugo` 就填的是 `D:\hugo` 就可以了.

注意：`win10`以下系统界面不一样，比如`win7`，直接在path最前或最后加入地址就行，注意用英文;分号分割开，不会的小白可以问度娘。
配置好后点击确定，然后打开`cmd`命令行程序就可以在任意位置使用hugo命令了。

### hugo新建博客

win+R键打开运行框，输入cmd打开命令行。

使用如下命令

```shell
    hugo new site /path/to/site
```

比如 `hugo new site E:/hugo/hojunBlog` 就在E盘hugo文件夹下新建了一个叫 `hojunBlog` 的hugo站点。

hugo新建页面和文章
新建一个`links`页面：

```shell
   hugo new links.md
```

links.md 自动生成到了 `content/links.md` 内容如下

```html
   ---*
*

   title: "Links"
   date: 2020-09-02T23:35:53+08:00
   draft: true
   ---*
*

```

创建第一篇文章，放到 `post` 目录，方便之后生成聚合页面。

```shell
   hugo new post/myfirst.md
```

links.md 自动生成到了 `content/post/myfirst.md` 内容如下:(注意这里需要把draft删除掉，不然正式生产的时候不会生成文章，因为draft是草稿)

```html
   ---*
*

   title: "Myfirst"
   date: 2020-09-02T23:23:34+08:00
   draft: true
   ---*
*

```

### hugo安装主题

新建文章后不要着急，还需要安装hugo主题才行。去官方主题列表 [themes.gohugo.io](https://themes.gohugo.io) 里去挑选自己想要的主题。

我们这里以`icarus`主题为例来安装主题。Github仓库地址 [Github.com/digitalcraftsman/hugo-icarus-theme](https://Github.com/digitalcraftsman/hugo-icarus-theme)

根据文档`clone`主题
在Hugo站点运行的文件夹中

```shell
   cd themes
   git clone https://Github.com/digitalcraftsman/hugo-icarus-theme.git
```

### 配置主题

找到icarus主题下的`hojunBlog\themes\hugo-icarus-theme\exampleSite\config.toml`复制其内容到根目录下的`hojunBlog\config.toml`中，接着修改根目录下的配置文件部分内容如下：

```html
   baseurl = "https://yourname.Github.io"
   languageCode = "en-us"
   title = "Icarus"
   # Enable comments by entering your Disqus shortname
   disqusShortname = "spf13"
   # Enable Google Analytics by entering your tracking code
   googleAnalytics = ""
   # Define the number of posts per page
   paginate = 10
   footnotereturnlinkcontents = "↩"
   theme = "hugo-icarus-theme"
   # Comment the themesDir option if you use this theme in production
   themesDir = "./themes/"
```

其中重要的是 `baseurl` 、`theme`、`themesDir`的配置，其他的配置可以之后慢慢设置。baseurl需要改成你的Github pages的仓库名，theme、themesDir改成主题目录名和主题路径（文件夹相对路径）。
其他配置可以参考`icarus`主题的文档，这里就不做介绍了。

使用命令来预览、发布主题
在根目录（比如这里是`hojunBlog`下）执行：

```shell
   hugo server
```

然后打开浏览器，输入`localhost:1313`就可以看到自己的博客了！（注意之前说的文章里的`draft: true`要删掉哦）

接着就是要发布主题到Github上了，注册Github，新建`yourname.Github.io`的仓库，配置`SSH`，复制仓库的`Github pages`地址到之前说的配置的`baseurl`中(就是yourname.Github.io)，这些步骤不会的可以去百度找教程，这里就不熬述了。

最后然后使用命令：

```shell
   hugo
```

就可以发布到Github上，通过 [https://yake.tk](https://yake.tk) 访问你的博客了！

当然如果你有自己域名还可以自定义域名.

### The End

hugo搭建博客教程就到这里了，欢迎大家加入讨论

注意： 本博客使用 Hexo 制作.
