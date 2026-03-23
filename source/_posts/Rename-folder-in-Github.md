---
title: Rename folder in Github
tags: github
categories: 技术
excerpt: 一个在Github网页版重命名仓库文件夹的实用技巧
date: 2025-08-10 16:13:08
---

昨天想着新建一个`Albums`页面来存放自己最近几天画的一些作品（是的，你可以在导航栏找到它），然后捣鼓了半天，好不容易把图标弄出来，发布到github仓库的时候，在浏览器打开发现网站提示`Page not found`, 我当时还以为是没deploy成功，反复提交几次，还是不行，但是本地运行是可以看见`Albums` 页面的，查来查去发现问题出现在Github文件。

## 问题

在GitHub上面我的文件夹是`Albums`，而在本地的文件是`albums`，我最开始创建这个文件夹的时候是大写的Albums，中间提交了一次，后面在本地改成小写了，又提交了一次，但是这个改动却没有同步到Github。

---

我发现这个问题后，觉着很奇怪，为啥文件夹名称改动没同步过去？

开始的时候我试着直接在github重命名文件夹，发现没有这个选项😢，只有单个文件可以重命名，搜了一下发现这是GitHub老毛病了😧，确实不能随便改动，严谨得不适应，查了几种办法发现都有点麻烦，最后在B站找到一个比较简单的办法。

## 解决办法

在你要重命名的仓库界面，按下键盘上`>`键，会出现VS Code 界面，直接在里面重命名你的文件夹，然后提交（push），填一下commit就可以了，回到仓库界面刷新一下，就可以看到重命名的文件夹了。

B站视频链接：[github快速更改文件夹名称]( https://www.bilibili.com/video/BV17o4y1W7xy/?share_source=copy_web&vd_source=23140a93d8194736c57285b7afd9fa45)

---

## 为什么文件名称大小写会影响页面？

我发现，GitHub Page的网址路径，是以文件夹名字作为子路径，例如我博客的首页是`://he1219.github.io`，那我的Albums页面所在的路径是（文件夹名称为albums）`he1219.github.io/albums/`,子路径取决于文件夹名称。

而我设置的`/albums/`地址之所以找不到也是因为GitHub对应的文件夹不匹配，地址在`/Albums/`自然找不到，于是乎`Page not found`。

---
## 补录

难绷，我写完这篇博客，刚发布到GitHub上面就发现`Albums`他回来了😭😫，说实话，我当时真想开骂了💢，

问了一下chatgpt，他讲这是hexo推送git page老毛病了，既然是老毛病那就治治啊，总不能倚老卖老坑人啊。

> 这是 Hexo + GitHub Pages 的一个常见坑，原因有两个：
>
> ------
>
> ## **原因**
>
> 1. **GitHub Pages 上还有旧的生成文件**
>    - 你改了文件夹名后，Hexo 生成的新文件夹上传了，但旧的 HTML 文件还在 GitHub 仓库里，没有被覆盖（因为名字变了）。
>    - GitHub Pages 会保留这些旧文件，所以访问旧 URL 还是能打开，而新 URL 可能没生成或者没更新。
> 2. **Hexo 缓存没清理干净**
>    - Hexo 默认只会增量更新，文件名变化时需要手动清理。

不过后面我在album加了个`permalink: "/albums"` 重新生成推送GitHub，发现Albums文件夹没了，然后我又删了permalink，再重新生成推送，这下就好了，albums成功入驻仓库😩，不知道下次是否还会出问题， 没更新这篇博客就是没问题。

