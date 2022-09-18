---
title: "Giscus - 给 Github Pages 添加评论系统"
date: 2022-09-18
tags:
- Github_Pages
---

## 简介
Giscus 是一个由 GitHub Discussions 驱动的评论系统。用户登录 Github 账号授权后，就可以在你网站上评论了。配置简单，使用方便。

类似的评论系统还有 [gitalk](https://github.com/gitalk/gitalk) 和 [utterances]([utterances](https://utteranc.es/)) ，不过这俩是基于github issue 功能的评论系统，通过新建 issue 来进行回复，没有基于 github discussion 的 Giscus 好用。

### 基本信息
- 软件名：Giscus
- 官网地址： https://github.com/giscus/giscus
- 开发者：laymonage
- 安装地址： https://giscus.app/zh-CN

## 安装配置
按照 https://giscus.app/zh-CN 配置指导来就行。

- 安装 [Giscus App](https://github.com/apps/giscus)，并授权访问你的仓库。
- 前往 [Giscus 页面](https://giscus.app/zh-CN) 进行配置。
- 最后把生成的脚本加到你的页面中即可。

**遇到问题：**
`页面 ↔️ discussion 映射关系` 这项当前对于中文页面会显示乱码，因为对路径进行 url 编码了，可以改成 `页面 title`。


