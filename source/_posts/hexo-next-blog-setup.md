---
title: 用 Hexo + NexT 搭建技术博客
date: 2026-11-06 18:35:00
categories:
  - 技术
tags:
  - Hexo
  - 博客
---

这篇示例文章记录了一套 Hexo + NexT 技术博客的最小搭建流程，可直接作为你第一篇文章的模板。

<!-- more -->

## 1. 初始化工程

全局安装 Hexo 命令行工具后初始化：

```bash
npm install -g hexo-cli
hexo init hexo-blog
cd hexo-blog
npm install
```

## 2. 安装 NexT 主题

从官方仓库浅克隆到 `themes/next`，并在站点配置里启用：

```bash
git clone --depth 1 https://github.com/next-theme/hexo-theme-next themes/next
```

```yaml
# _config.yml
theme: next
```

## 3. 技术向配置要点

- 主题布局选 `Mist`，侧边栏展示分类与标签
- 开启代码块复制按钮与语言标识，方便读者拷贝代码
- 文章里用 `<!-- more -->` 控制首页摘要长度

## 4. 写作与发布

```bash
hexo new "文章标题"   # 新建文章
hexo clean && hexo g  # 清理并生成静态页面
hexo s                # 本地预览 http://localhost:4000
```

确定部署平台后，把站点配置里 `deploy` 段的注释打开并填入仓库地址，执行 `hexo d` 即可发布。
