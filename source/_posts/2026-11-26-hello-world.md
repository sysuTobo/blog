---
title: 开博客了
date: 2026-11-26 15:40:00
categories: 随笔
tags:
  - 博客
  - GitHub Pages
---

用 Hexo + NexT 在这台机器上搭了个静态博客，托管在 GitHub Pages。

<!-- more -->

首页按日期倒序列出文章，`Archives` 按年月归档，`Categories` / `Tags` 自动聚合，RSS 在 `/atom.xml`。

写新文章的流程：

```bash
cd ~/work/blog
export PATH=$HOME/work/.node/bin:$PATH
npx hexo new "文章标题"
$EDITOR source/_posts/2026-11-26-文章标题.md
npx hexo server        # 本地预览 http://localhost:4000/blog/
```

发布：

```bash
npm run deploy         # clean + generate，然后 push 到 gh-pages 分支
```

文章开头用 front matter 填 `title` / `date` / `categories` / `tags`；`<!-- more -->` 以上是首页摘要。草稿用 `hexo new draft`，确认后 `hexo publish`。
