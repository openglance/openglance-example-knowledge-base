---
title: OpenGlance 使用指南 Demo
type: user-guide-demo
status: maintained
canonical: false
source_repository: openglance/openglance
source_path: docs/user-guide.zh-CN.md
source_revision: 6f675a0
last_updated: 2026-09-06
ai_snippet: "[使用指南] 在一个公开仓库中体验 OpenGlance 阅读、文档改动提示、编辑、Mermaid、MDX-lite、Agent Context、Sync 与链接"
---

# OpenGlance 使用指南 Demo

[English](user-guide.md) | 简体中文

这份文档是正式 [OpenGlance 用户手册](https://github.com/openglance/openglance/blob/main/docs/user-guide.zh-CN.md)
的可操作配套版本。它把主要使用路线压缩成一页，并链接到可以直接体验相应交互的文件。

## 1. 打开一个普通 Git 仓库

OpenGlance 直接打开已经存在于本机的 Git 仓库，不会上传仓库，也不会再复制一套文档。目录、Git 历史和源文件
仍然可以由其他 Git 工具、编辑器与 Agent 使用。

本仓库里的内容直接介绍 OpenGlance，因此演示和截图中出现的文字也属于项目上下文。

打开多个仓库时，可以点击当前仓库名称旁的仓库按钮，或在 macOS 按 `Command+O`、在 Windows 按
`Ctrl+O`。窗口中央的仓库面板可以搜索顺序稳定的仓库列表；面板打开期间，`Command+1` 至
`Command+9`（Windows 为 `Ctrl+1` 至 `Ctrl+9`）会选择标有相应数字的可见仓库，`Command+0` 或
`Ctrl+0` 会打开另一个本机仓库。拖动仓库行左侧手柄可以上下调整并保存顺序；手柄获得焦点时，也可以
使用上下方向键，面板中的数字快捷键会立即重新编号。仓库行还可以从 OpenGlance 中移除，但不会删除本机文件；
worktree 选择器仍与仓库面板相互独立：存在多个 worktree 时，它会取代侧栏头部重复的仓库名称，仓库按钮仍显示在右侧。

## 2. 在 Preview 中阅读

Preview 用于只读浏览渲染后的 Markdown 或 MDX。文档仍保留来源行号，右侧目录会跟随页面中的 H1–H5
标题；唯一且位于开头的 H1 作为文档标题。跳过的标题级别会自动压缩，因此 H3 后直接使用 H5 时，
导航仍然只缩进连续的两级，不会留下空层级。

打开 [Markdown 与 Live](../demos/markdown-live.md)，依次尝试：

1. 从文档目录跳到一个标题；
2. 打开内部文档链接；
3. 选择几行带来源的准确内容；
4. 在 macOS 使用 Command-click、在 Windows 使用 Ctrl-click 打开第二个 Tab。

## 3. 在 Live 中做小范围修改

Live 在直接编辑原始 Markdown／MDX 的同时，让常见文档结构保持易读。它适合小幅修正、列表、链接、图片和
原生 Markdown 表格。

打开 [Markdown 与 Live](../demos/markdown-live.md)，切换到 Live，修改一个清单项。文件会自动保存到本地
工作区，但提交并推送以前不会被共享。

## 4. 在 Source 中检查准确源码

Source 同时显示准确的 Markdown、MDX、Frontmatter 和结构化组件数据。语法本身很重要，或者需要仔细检查
Agent 写入的内容时，使用 Source。

在同一个页面切换 Preview、Live 与 Source。它们是同一个文件的三种视图，不是三套文档格式。

## 5. 编辑原生 Markdown 表格

在 Live 中，原生管道表格会保持渲染状态：

- 单击单元格，只编辑这个单元格的源码；即使仍在编辑，也可以从编辑框拖入相邻单元格扩大选区；
- 横向、纵向或斜向拖动，选择起点与终点围成的矩形；
- 使用固定在表格上方的格式工具栏设置粗体、斜体、删除线、前景色或文字后方的高亮色；
- 对齐选区涉及的整列；清除文字格式时保留列对齐；
- 两个固定色板只在需要时展开，工具栏可通过关闭按钮或 Esc 关闭；
- 在同一列纵向选中至少两个单元格后，使用列拖动把手移动整列。

Preview 始终只读。保存后的内容仍然是原生管道表格、标准 Markdown、分隔行对齐与受控内联样式，可以继续
在 Obsidian 中打开。

完整场景见 [Live 表格编辑](../demos/live-table-editing.md)。

## 6. 处理图片

当图片需要明确宽度、对齐或说明文字时，Live 可以把 Markdown 图片转换为受控的 HTML 图片行。源码仍然
可以检查，并且只保留安全的图片属性。

打开 [图片编辑](../demos/image-editing.md)，切换到 Live，然后选择 OpenGlance 图标。

## 7. 阅读 Mermaid 架构图

标准 Mermaid 围栏仍是可移植的 Markdown。OpenGlance 在 Preview 和 Live 的非活动区块中本地渲染，同时
保留完全相同的源码和行范围。

打开 [Mermaid 图](../demos/mermaid-diagrams.md)。在复杂 flowchart 中，确认“智能阅读”会纵向呈现完整
拓扑，不显示节点选择器，也不生成丢失上下文的局部小图；关闭并重新打开“智能阅读”，确认每个节点和关系
都仍然存在。继续尝试“适应宽度”、缩放、拖动画布，并用 `</>` 检查准确源码。把这个完整阅读视图与明确
指定行列和留白的 `block-beta` 图比较；随后切换到 Live，确认光标不在源码行内时仍显示图形。

## 8. Agent 读数据，人看结构化视觉

OpenGlance MDX-lite 只接受有限的组件集合，组件数据仍然是普通 CSV、TSV、JSON 或 Markdown 文本。`Chart`
和 `DataTable` 还可以引用仓库内的 `.dataset.json` 数据契约，以及旁边长期维护的全量 CSV 或 JSON 数据文件。
报表指定包含首尾日期的区间，读者只能选择源数据粒度可靠支持的视图：日数据支持日、周、月和自然季度，
周数据只支持周；切换视图不会改动源数据。

OpenGlance 不会执行任意 JSX、import、脚本或事件处理器。数据集聚合只使用清单里明确声明的字段类型和汇总规则。

在 Live 中，单击已渲染的组件会保持视觉呈现，并打开一个紧凑工具栏。`DataTable` 提供常用表格设置，
`Chart` 提供类型和数值标签，`DecisionBox` 提供状态。无论数据在文档内还是来自外部，每个组件都只通过
一个 `</>` 入口进入源码。关闭按钮、Esc 或选择其他对象都能关闭工具栏。

数据集的日、周、月、季度按钮仍是组件内部的阅读控件。它们不会打开编辑工具栏，也不会写入 MDX。

打开 [MDX-lite 组件](../demos/mdx-lite-components.mdx)，在 Preview、Live 与 Source 中检查 DataTable、
Timeline、Chart、DecisionBox、MetricGrid 和 FlowDiagram；在外部数据集一节，把同一份日数据切换到四种
时间粒度。然后打开独立的 [外部数据集报表](../demos/external-dataset-report.mdx)，检查三文件契约、日期区间、
带类型的筛选条件、预期季度结果，以及周数据源唯一可靠的周视图。

## 9. 把准确上下文交给 Agent

带来源的行选择让离开 App 的内容仍然保留仓库路径和源码行号。还可以把多个片段整理成 Agent Context，再
交给外部 Agent。

打开 [Agent Context 与 Sync](../demos/agent-context-and-sync.md)，完成其中限定范围的选择练习。

## 10. 有意识地检查和发布改动

自动保存只负责写入本地文件。Sync 显示尚未发布的文件和远端状态；发布始终是明确的 Git 操作。OpenGlance
不会静默发布未完成内容，也不会自动重写已经分叉的历史。

发布前可以在 Sync 中选填“本次修改摘要”。留空时，App 在本地根据改动文件及本次新增或修改的文档变更
摘要生成说明，不会重复使用未变化的历史记录。[Agent Context 与 Sync](../demos/agent-context-and-sync.md)
Demo 提供了摘要草稿练习。

[Agent Context 与 Sync](../demos/agent-context-and-sync.md) Demo 提供了一个可以修改、随后撤销的
无害练习。完成修改后：

- Preview、Source 与 Live 会用低干扰暖色提示当前新增和替换内容；
- 受影响章节在文档导航中铺满整行底色，点击仍跳到同一标题；首个可见标题以前的改动归入“文档顶部”；
- 删除一个可见词语后，紧凑、默认关闭的“显示删除内容”开关会出现；开启时图标右上角显示实心状态点，
  只给只读删除文字增加删除线，不另加颜色，原有当前文档行号保持不变；
- 打开另一个文档再返回时，OpenGlance 会根据提交版本与当前文件重新生成同样的提示。

这是一项文档定位能力，不是完整 Git diff 或暂存界面。体验完成后，请撤销练习改动。

## 11. 保持工具边界

OpenGlance 适合阅读、检查和小范围编辑仓库上下文。大范围代码修改应使用完整编辑器；复杂冲突使用 Git 合并
工具；更大的仓库任务交给外部 Agent。

返回 [Demo 首页](../README.zh-CN.md)，或查看
[OpenGlance 正式文档](https://github.com/openglance/openglance/tree/main/docs)。
