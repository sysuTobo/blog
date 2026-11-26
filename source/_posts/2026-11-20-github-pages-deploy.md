---
title: GitHub Pages 部署备忘
date: 2026-11-20 21:00:00
categories: 技术
tags:
  - GitHub Pages
  - Hexo
---

记录一下这套站点的发布方式，免得以后忘了。

<!-- more -->

## 两种站点形态

- 仓库名 `sysuTobo.github.io` → 根站点，地址 `https://sysutobo.github.io/`，`_config.yml` 里 `root: /`
- 任意仓库名（这里是 `blog`）→ 项目站点，地址 `https://sysutobo.github.io/blog/`，`root: /blog/`

现在用的是后者，仓库里 `_config.yml` 的 `url` / `root` 已按 `/blog/` 配好。

## 发布

构建产物不提交到 `main`，而是由 `hexo-deployer-git` 推到 `gh-pages` 分支：

```bash
npm run deploy
```

GitHub 仓库 Settings → Pages → Source 选 `Deploy from a branch`，分支 `gh-pages`、目录 `/ (root)`。

## 自定义域名

仓库根目录放一个 `CNAME` 文件，内容是域名；再到 DNS 加一条 CNAME 指向 `sysutobo.github.io`。HTTPS 证书由 GitHub 自动签发。
