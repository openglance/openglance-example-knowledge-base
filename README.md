# OpenGlance User Guide Demo

English | [简体中文](README.zh-CN.md)

This is the public, runnable companion to the
[OpenGlance](https://github.com/openglance/openglance) user guide. The repository content is about
OpenGlance itself, so the same pages remain meaningful when they appear in product screenshots, onboarding
walkthroughs, or manual acceptance checks.

OpenGlance is the human interface over an ordinary local Git repository. People read, inspect, and make
focused edits in OpenGlance; agents and developers work with the same files through Git and their usual
tools.

## Try it in OpenGlance

1. [Install OpenGlance](https://gitleaf.mangofuture.com/download).
2. Clone this repository:

   ```bash
   git clone https://github.com/openglance/openglance-example-knowledge-base.git
   ```

3. Open the cloned folder in OpenGlance.

If OpenGlance is already installed, use
[Open in OpenGlance](https://gitleaf.mangofuture.com/open?repo=openglance%2Fopenglance-example-knowledge-base&path=README.md).

## Start with the guide

- [OpenGlance user guide demo](guide/user-guide.md) — a concise product tour whose links open the
  matching runnable examples.
- [简体中文使用指南 Demo](guide/user-guide.zh-CN.md) — the same tour in Simplified Chinese.

## Main feature demos

| Demo | What to try |
| --- | --- |
| [Link previews](demos/link-previews.md) | Hover over local documents, sections, source lines, and GitHub links using the local gh login |
| [Markdown and Live](demos/markdown-live.md) | Preview, outline, Source, Live, frontmatter, links, lists, and tasks |
| [Live table editing](demos/live-table-editing.md) | Cell editing, rectangular formatting, text highlight, column alignment, and movement |
| [Image editing](demos/image-editing.md) | Markdown images and the Live image toolbar |
| [Mermaid diagrams](demos/mermaid-diagrams.md) | Vertical Smart view, complete topology, source fallback, and Live preview |
| [Agent Context and Sync](demos/agent-context-and-sync.md) | Source-backed line selection, document edit cues, a focused edit, and deliberate publishing |
| [MDX-lite components](demos/mdx-lite-components.mdx) | Six safe component toolbars plus source-granularity-aware external reports |
| [External dataset report](demos/external-dataset-report.mdx) | Daily and weekly sources, typed manifests, bounded ranges, filters, and safe time views |

## How this repository is maintained

The canonical product documentation remains in the OpenGlance source repository. This demo records the
upstream source revision on adapted pages and is reviewed whenever a stable user-visible workflow or
screenshot scenario changes. It intentionally excludes private data, arbitrary executable MDX, and
regression-only edge cases.

Except for the explicitly labeled MDX-lite demo, the examples stay compatible with Obsidian and other
tools that support ordinary Markdown, GFM tables, and safe inline HTML.

## License

This repository is licensed under the [Apache License 2.0](LICENSE), matching OpenGlance.
