---
title: Link preview demo
type: feature-demo
status: maintained
canonical: false
source_repository: openglance/openglance
source_path: docs/user-guide.md
source_revision: 15fa38e0ddd2ad4814d07faf7c3ba2ad394d6a90
last_updated: 2026-09-19
description: Read local document excerpts and GitHub context before opening a link in OpenGlance.
---

# Link previews

In Preview or Live, pause over any supported link below. Move into its card to keep reading, expand the
excerpt, or choose **Open**. Press `Escape` to close it. In Preview, focus a link with the keyboard and
press `Alt+Down` to enter its card.

The compact card puts its title and close button on the same row, followed by the path and excerpt.
Milestone progress and other resource details remain visible where relevant.

## Local documents

- [Whole document: Markdown and Live](markdown-live.md) uses the document's saved summary.
- [One section: Three views, one source file](markdown-live.md#three-views-one-source-file) shows that
  section instead of the whole-document summary.
- [Exact source lines](markdown-live.md#L11-L14) shows the original source with frontmatter included in
  the line numbering.

The preview reads the local saved file. Hovering does not edit, synchronize, or publish it.

## GitHub context

- [OpenGlance repository](https://github.com/openglance/openglance) shows repository information.
- [OpenGlance README](https://github.com/openglance/openglance/blob/main/README.md) shows a file excerpt.
- [OpenGlance user guide](https://github.com/openglance/openglance/blob/main/docs/user-guide.md) and
  [architecture](https://github.com/openglance/openglance/blob/main/docs/architecture.md) let you try
  different file previews over the same network connection.
- [Latest OpenGlance release](https://github.com/openglance/openglance/releases/latest) shows release
  information when the repository has a published release.

GitHub previews use the current local GitHub CLI (`gh`) login. If needed, install `gh` and run
`gh auth login`. Issue, pull request, milestone, and commit links are also supported. Milestone cards
show the description, open/closed state, due date, and closed/total Issue and PR counts. A milestone
without any items shows an empty state rather than a completion percentage. Private repositories follow
your account's existing permissions; use a link from your own authorized repository to try that path.
This public demo does not contain private repository addresses or content.

The card explains missing login, missing content, denied access, or connection errors. GitHub file line
anchors are supported; other GitHub anchors show a labeled resource excerpt rather than comments or
diffs. Different GitHub URLs reuse the same connection; file branch and tag lookups can run concurrently
over HTTP/2. The first connection and each API read still take network time. Successful previews stay
in memory for up to 60 seconds.
Try hovering the same link again: it should appear faster. Switching the local `gh` login or logging out
clears retained content; status and Milestone progress may be up to one minute old when a card opens.
Content is not sent to an AI service or saved in a disk cache.

## External previews in Codex and other clients

Copy this [OpenGlance document link](https://gitleaf.mangofuture.com/open?repo=openglance%2Fopenglance-example-knowledge-base&path=demos%2Flink-previews.md&title=Link+preview+demo)
into a preview-capable client. The hosted response supplies the document title, repository path,
OpenGlance site name, and a small icon. The client decides which fields to show and how long to cache
them; a hover card is not guaranteed in every application. No large cover image or document-body
summary is sent. Clicking still opens the local document in OpenGlance.

New links from the generator carry a title of up to 100 characters. Use `--no-preview-title` to omit a
sensitive title. Older links without a title use the filename. Repository permissions do not hide
metadata embedded in a URL from its recipients or preview services.

在 Codex 等支持链接预览的客户端中，上面的 HTTPS 链接会提供文档标题、仓库路径、OpenGlance 来源和小图标。
实际卡片显示和缓存由客户端决定。生成器默认携带最多 100 字符的标题，敏感标题可用
`--no-preview-title` 省略；旧链接回退到文件名。正文和 AI 摘要不会传输，点击仍在本机 OpenGlance 中打开文档。

## 中文操作提示

在 Preview 或 Live 中，将鼠标停在上面的链接上；移入卡片可继续阅读、展开摘录或打开链接，按 `Esc`
关闭。紧凑卡片将标题和关闭按钮放在同一行，下方展示路径、摘录及适用的里程碑进度等信息。
本地链接分别演示整篇摘要、单个章节和准确源文件行。GitHub 预览使用本机 `gh` 的当前登录权限；
私有仓库可以使用自己的已授权链接体验，无需把私密内容加入这个公开 Demo。Milestone（里程碑）链接
会展示描述、状态、截止日期和 Issue／PR 关闭进度；没有事项时显示空状态。不同 GitHub 链接共用连接，
支持 HTTP/2 时文件预览的分支和标签查询可并发执行；首次建连和每次 API 读取仍需要网络时间。成功
预览在内存中保留最多 60 秒，再次悬停同一个链接会更快。切换 `gh` 登录或退出账号后清除旧内容；卡片
打开时的状态和进度可能延迟最多一分钟，内容不会写入磁盘缓存。

[Return to the guide](../guide/user-guide.md) · [返回中文指南](../guide/user-guide.zh-CN.md)
