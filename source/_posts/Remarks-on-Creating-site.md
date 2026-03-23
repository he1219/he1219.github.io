---
title: Remarks on Creating site
date: 2025-08-03 16:51:53
tags: "建站"
categories: "技术"
excerpt: 这篇文章主要记录一下搭站的过程中遇到的一些问题。
---

## 前言

在磕磕撞撞地弄了一周后，终于建好了自己的博客，这篇文章我主要记录一下搭站的过程中遇到的一些问题。
有的问题折磨了我很久，记下来也好让后面的有心人参考。话不多说，直奔主题。

## Hexo部署

这个过程我参考的是这篇blog: [Hexo教程，看这一篇就够了- How to系列](https://blog.csdn.net/cat_bayi/article/details/128725230)，
这里面内容非常详细，没弄过的小白也能上手（我也是小白😁）。按照这篇教程一步一步去安装必要的程序和软件，直到**个性化主题**那里。

### Fluid主题安装

我用的Hexo主题跟那篇博客演示的主题是一样的，具体的样式可以去官网[Hexo Theme Fluid](https://hexo.fluid-dev.com/)看看。如果你也想采用Fluid主题的话，可以直接参考这篇官方用户手册[开始使用 | Hexo Fluid 用户手册](https://hexo.fluid-dev.com/docs/start/#%E4%B8%BB%E9%A2%98%E7%AE%80%E4%BB%8B)。**不推荐**按照CSDN博客里面的流程去安装Fluid主题。

### 评论区插件安装

我的blog采用的是Waline评论插件，样式可以在文章底部见到，具体部署流程可参考官方文档[快速上手 | Waline](https://waline.js.org/guide/get-started/)

**注意！！！**

不要用Vercel部署服务端，Vercel部署成功后分配给你的域名在国内不可访问（被墙），需要绑定可访问的域名（你自己的域名）。推荐使用Netify部署，详见文档[Netlify 部署 | Waline](https://waline.js.org/guide/deploy/netlify.html)。

同时HTML（客户端）也不需要自己去部署，Fluid内置Waline评论插件，我们只需要把服务端部署好后，将服务器URL写到Fluid配置文件即可。

---

## 域名的相关问题

说到域名，搭blog的一周里面3-4天是被域名折磨的，起初是因为Vercel分配的应用域名被墙，想要申请一个新域名来绑定，以此来继续使用评论插件，前前后后申请了4个域名，前三次是免费域名，但都是子域名，第一次申请`hoffen.js.org`， 没通过，人家不办理非Java个人博客类的子域名了，这是人家原话：

> Due to the high number of requests we no longer hand out subdomains for personal blogs or pages without a distinct connection to JavaScript.
> But there are a variety of similar services that may fit better.

还好心的给我推荐了几个子域名申请网址，于是乎我又申请了另一个子域名`hoffen.js.cool`，这个是国人主持的项目，申请界面非常人性化（傻瓜式操作），比github`Pull Request`直观多了，不过到现在我也不知道通过了没有🤔，也没有通知，只能当作寄了。

第三次我直接搜索“免费域名”，在众多网页里面选了一家网站：聚域网，又注册了一个子域名`hoffen.eu.cc`，然后这次我可以管理域名解析记录，想要绑定新域名到Vercel的应用域名，发现域名验证一直过不去，卡了好几天，家里网络也不稳定，直连Github也经常上不去，快要急死我了，试了几次，实在受不了这种折磨，便放弃了😭。

最后在阿里云买了个二级域名`hoffen.fun`，才绑定成功，不过同时我也发现Netlify部署的网址没被墙，新域名又显得多余了，看着这么简洁的域名（跟GitHub page 默认域名相比），我把它换成了blog网址。总之，我的经验是子域名大多是免费的，但是绑定其他域名有困难，有域名需求的可以考虑去腾讯云或阿里云申请一个，十几块钱就能买一个。

---

## PS：恭喜天禄TYLOO在裂变天地赛事夺冠！！！

在我搭blog期间，正值裂变天地赛事开赛期，中国战队天禄TYLOO于7.21战胜丹麦A队，夺得冠军，世界排名来到NO.7，创造历史!

![TYLOO](https://i0.hdslb.com/bfs/new_dyn/8305609b44e06c3ba5dd63dbac3d0593373076765.jpg)
