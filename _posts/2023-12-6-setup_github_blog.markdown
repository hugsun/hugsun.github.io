---
title: "基于github搭建个人blog😀"
layout: post
date: 2023-12-6 11:30
# image: /assets/images/markdown.jpg
headerImage: false
tag:
- 技术
# star: true
# hidden: true
category: blog
author: hugsun
description: 记录搭建github blog的过程
---

# 前言😀

身为技术人员，时常归纳总结自己的技术沉淀是必要的。blog就是个不错的文档发布渠道，不仅可以作为技术名片，也多了个表达渠道。

## 什么是github page?

GitHub Pages 是一项静态站点托管服务，它直接从 GitHub 上的仓库获取 HTML、CSS 和 JavaScript 文件，（可选）通过构建过程运行文件，然后发布网站，[关于github pages](https://docs.github.com/zh/pages/getting-started-with-github-pages/about-github-pages)。 

没有github账号的同学得抓紧注册一个！

## 目标需求

初步搭建需求很简单，如下：

- [ ]  能发布文章
- [ ]  正常展示
- [ ]  干净的排版

基于上述需求，我确定了模板为https://github.com/sergiokopplin/indigo

# 实现步骤

## 1. 新建项目

打开你的github主页，点击create new → New repository

![Untitled](/assets/2023/setup_github_blog/Untitled.png)

然后，定义你的仓库名为 NAME.github.io，选择为Public项目，也可以把Add a README file勾上，然后Create repository

![Untitled](/assets/2023/setup_github_blog/Untitled%201.png)

## 2. 为项目添加代码

首先，clone目标模板代码https://github.com/sergiokopplin/indigo，将其copy到新建的个人blog仓库下。

然后，打开_config.yml文件，对其进行编辑，将配置设置成自己的仓库设置。尤其是url, 一定要定义成https://NAME.github.io的格式（买了自己域名的换成购买域名即可）。

![Untitled](/assets/2023/setup_github_blog/Untitled%202.png)

添加配置”timezone: Asia/Shanghai” 

![Untitled](/assets/2023/setup_github_blog/Untitled%203.png)

作者信息和社交账号也一样修改成自己的，assets/images/profile.png也可以替换成自己喜欢的头像

![Untitled](/assets/2023/setup_github_blog/Untitled%204.png)

都修改完毕后，git push你修改过配置的代码

## 3.仓库设置

打开blog仓库，点击Settings→Pages，然后点击设置Source和Branch(这里选择你代码上传的分支即可)

![Untitled](/assets/2023/setup_github_blog/Untitled%205.png)

设置完毕之后，稍作等待就好。github-pages的部署可能会需要点时间，等这里的显示变成active了，就说明部署完毕。

![Untitled](/assets/2023/setup_github_blog/Untitled%206.png)

点击github-pages→View deployment

![Untitled](/assets/2023/setup_github_blog/Untitled%207.png)

就可以看到自己的个人blog了😁

![Untitled](/assets/2023/setup_github_blog/Untitled%208.png)

# 添加blog

## 1.安装jekyll

因为我们的blog模板是基于jekyll开发的，所以想本地调试需要安装相关依赖，[安装手册](https://jekyllrb.com/docs/installation/)。在手册中根据自己的系统平台安装即可。

## 2.本地调试

在项目仓库下的_posts文件夹中添加一篇blog，**命名格式为：yyyy-mm-dd-filename.markdown** (filename尽量用英文)

![Untitled](/assets/2023/setup_github_blog/Untitled%209.png)

添加完毕后在项目根目录下打开命令行，运行

```bash
bundle exec jekyll serve
```

如果windows上报错，需要暂时注释_config.yml中的timezone: Asia/Shanghai

```bash
No source of timezone data could be found. (TZInfo::DataSourceNotFound)
```

启动成功后打开http://localhost:4000/ 就可以看到当前的post了，不合适的样式或错别字都可以更改。