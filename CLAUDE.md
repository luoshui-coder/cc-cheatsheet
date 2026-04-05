# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是 **Claude Code 速查表**的静态网站，部署于 GitHub Pages（`https://cc.storyfox.cz/`）。

整个网站是单个自包含的 `index.html` 文件：所有 CSS、JavaScript、内容均内联其中，无构建步骤，无依赖。

## 部署

推送到 `main` 分支后，`.github/workflows/deploy.yml` 会自动触发 GitHub Pages 部署（整个仓库根目录作为静态资源上传）。

## 文件结构

- `index.html` — 网站全部内容（CSS + HTML + JS 全部内联）
- `.github/workflows/deploy.yml` — GitHub Pages 自动部署工作流

## index.html 内部结构

页面采用 **4 列网格布局**（`main-grid`），每列包含 2 个 section，共 8 个内容块：

1. 键盘快捷键（Keyboard）
2. 斜杠命令（Slash Commands）
3. 工作流（Workflows）
4. 技能与 CLI（Skills & CLI）
5. MCP 服务器（MCP Servers）
6. 记忆文件（Memory Files）
7. 配置（Config / Env Vars）
8. CLI 标志（CLI Flags）

每个 section 结构：`.section` > `.section-header` + `.section-content`，内部用 `.sub-header` 分组，内容行用 `.row` > `.key` + `.desc` 排列。

页面支持**中英文切换**（通过 JS 控制 `data-zh` / `data-en` 属性切换可见性），支持 **A4 横版打印**（`@page { size: A4 landscape }`）。

顶部有 changelog 横幅，可关闭（状态存于 `localStorage`）。

## 本地预览

直接在浏览器中打开 `index.html` 即可，无需任何服务器或构建工具。
