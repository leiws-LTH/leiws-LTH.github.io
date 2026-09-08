# 求索录

> 路漫漫其修远兮，吾将上下而求索。

个人博客：记录学习笔记、心得体会与日常生活。

- 框架：[Hexo](https://hexo.io/)
- 主题：[Butterfly](https://butterfly.js.org/)
- 托管：GitHub Pages（免费）
- 部署：GitHub Actions 自动构建，推送即发布
- 线上地址：https://leiws-lth.github.io

## 日常写作流程

### 1. 写一篇新文章

```bash
hexo new "文章标题"
```

会在 `source/_posts/` 下生成同名 Markdown 文件，打开编辑即可。

文章头部可以设置标签和分类：

```markdown
---
title: 文章标题
date: 2026-09-08 18:00:00
tags:
  - 标签名
categories:
  - 分类名
---
```

### 2. 本地预览

```bash
hexo server
```

浏览器打开 http://localhost:4000 实时预览，`Ctrl+C` 停止。

### 3. 发布

```bash
git add .
git commit -m "发布：文章标题"
git push
```

推送后 GitHub Actions 会自动构建并发布，约 1 分钟后线上生效。

## 目录结构

```
blog/
├── _config.yml              # 站点主配置（标题、作者、语言等）
├── _config.butterfly.yml    # 主题配置（菜单、外观、功能）
├── source/
│   ├── _posts/              # 所有文章（Markdown）
│   ├── about/               # 「关于」页面
│   ├── tags/                # 标签页
│   ├── categories/          # 分类页
│   └── img/                 # 本地图片
├── scaffolds/               # 文章模板
└── .github/workflows/       # 自动部署配置
```

## 常用操作备忘

| 操作 | 命令 |
| ---- | ---- |
| 新建文章 | `hexo new "标题"` |
| 新建草稿 | `hexo new draft "标题"` |
| 草稿转正式 | `hexo publish "标题"` |
| 本地预览 | `hexo server` |
| 本地构建 | `hexo generate` |
| 清理缓存 | `hexo clean` |

## 修改站点信息

- 站点标题 / 作者 / 描述：`_config.yml` 顶部 `# Site` 部分
- 菜单 / 外观 / 侧边栏：`_config.butterfly.yml`
- 「关于」页内容：`source/about/index.md`

改完记得提交推送：

```bash
git add .
git commit -m "更新配置"
git push
```

## 图片怎么放

1. 本地图片：放到 `source/img/` 下，文章里用 `![描述](/img/文件名.jpg)` 引用
2. 外链图片：直接使用图片 URL

## 首次部署（已完成，仅供备查）

1. 在 GitHub 创建名为 `leiws-LTH.github.io` 的公开仓库
2. 仓库 Settings → Pages → Build and deployment → Source 选 **GitHub Actions**
3. 本地执行：

```bash
git remote add origin https://github.com/leiws-LTH/leiws-LTH.github.io.git
git push -u origin main
```

## 在新电脑上继续写博客

```bash
git clone https://github.com/leiws-LTH/leiws-LTH.github.io.git
cd leiws-LTH.github.io
npm install
```

然后照常「写作 → 预览 → 推送」即可。
