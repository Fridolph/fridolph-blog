---
title: butterfly-新文章例子 #【必需】頁面標題
date: 2024-1-1 16:00:00 #【必需】頁面創建日期
updated: 2024-1-1 16:18:00 # 【可選】頁面更新日期
type: # 【必需】標籤、分類和友情鏈接三個頁面需要配置
description: 【可選】頁面描述
keywords: 关键字
---

按着官方文档来就好了，最好的例子就是文档啦。当然写博客的话，是为了记录一些需要留意的地方

## 搭建环境

- Nodejs: 12.16.0
- npm: 6.13.4
- hexo: 6.3.0
- hexo-cli: 4.3.1  直接hexo init 即可
- hexo-theme-butterfly: 4.12.0 

一定要看是否安装完对应依赖，大部分看似复杂的问题基本都是不经意的小地方造成。说多了都是泪

<!-- more -->

## 隐藏标签

如果想把一些文字、内容隐藏起来，并提供按钮让用户点击显示。可以使用这个标签外挂。

```md
 <!-- 行内用法 -->
哪个英文字母最酷？ {% hideInline 因为西装裤(C装酷),查看答案,#FF7242,#fff %}

门里站着一个人? {% hideInline 闪 %}

<!-- 块级用法 -->
查看答案
{% hideBlock 查看答案 %}

傻子，怎么可能有答案
{% endhideBlock %}

<!-- 折叠用法 -->
{% hideToggle Butterfly安装方法 %}

在你的博客根目录里
git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly

如果想要安装比较新的dev分支，可以
git clone -b dev https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly

{% endhideToggle %}
```

## 图片放本地 随文章路径

> 之前的想法很美好，CDN加速整个七牛云啥的，折腾了半天 = = 没充钱，现啥都没保留。暂时先算了，还是本地，服务器，和项目里各备份一份来得实在，github pages确实会慢不少，后续迁移到ECS里应该会快不少

这样写即可，`![头像](avatar.jpg)`

_config.yml 里设置

```yml
post_asset_folder: true
marked:
  prependRoot: true
  postAsset: true
```