---
title: Document comments demo
type: feature-demo
status: maintained
source_repository: openglance/openglance
source_path: docs/user-guide.md
source_revision: 36b3d84fa3232e0944b3762527c3af802e950fb4
last_updated: 2026-10-28
ai_snippet: "[Demo] Create and reply to Git-backed document comments, resolve with a clean body, reopen, and publish manually"
---

# Document comments

Use a build containing the document comments feature. If the installed release does not show **Comments**,
follow the upstream [source build guide](https://github.com/openglance/openglance/blob/main/docs/build-from-source.md).
This page is ordinary Markdown; the discussion records are readable at the end in Source.

## 1. Create and reply

Comments stay in the Markdown file. An agent can read the discussion without opening OpenGlance.

Drag to select part of the paragraph above, click **Add comment** beside the selection, check the quoted
passage, and save locally. Keyboard selections in Live and Source show the same contextual action.
Use the speech-bubble icon after **Copy share link** to open the right Comments panel.
Reply there; **New comment** becomes available after selecting text or source lines. Plain Preview paragraphs support exact text selection; complex
formatting explicitly falls back to a source-backed paragraph or line range. Live and Source use their
editor selections. Agent Context remains available in the left sidebar.

## 2. Resolve and inspect history

Resolving a discussion restores the document to normal reading. Publication remains a separate action.

Open a thread and choose **Resolve**. Its body marker disappears completely. Find the discussion under
**Resolved**: the original quote and replies remain, and inspecting them leaves the body normal. This
page also includes a resolved sample so that the history filter is usable on first open.

## 3. Reopen and publish deliberately

Choose **Reopen** on a resolved thread and return to **Open**. A marker returns when its quote can still
be located. Changing the underlying text does not automatically resolve a discussion. If a quote can no
longer be located, the panel preserves it and reports that it needs review.

Creating, replying, resolving, and reopening save only the local file. None of those actions commits or
pushes. Inspect the change in Sync; publish manually only when you want to share this demo's changes.
Message bodies initially display as inert text, retaining any Markdown syntax. The author field is a
local signature rather than a verified identity. MDX comments are not enabled.

<!-- openglance-comment:v1
{
  "id": "6936ed22-3c26-4161-8c1f-c1760d1ff8ec",
  "status": "open",
  "anchor": {
    "exact": "An agent can read the discussion without opening OpenGlance.",
    "prefix": "e.\n\n## 1. Create and reply\n\nComments stay in the Markdown file. ",
    "suffix": "\n\nSelect part of the paragraph above, click **Add comment**, che"
  },
  "messages": [
    {
      "id": "8edf0394-4c4d-4133-836b-5ea0b488b5e6",
      "author": {
        "name": "OpenGlance demo",
        "kind": "human"
      },
      "created_at": "2026-10-28T04:00:00Z",
      "body": "Can we show an example of an Agent replying through the same file?"
    }
  ]
}
-->

<!-- openglance-comment:v1
{
  "id": "aa490ca0-a801-4c4e-996f-122b59054a94",
  "status": "resolved",
  "anchor": {
    "exact": "Publication remains a separate action.",
    "prefix": "Resolving a discussion restores the document to normal reading. ",
    "suffix": "\n\nOpen a thread and choose **Resolve**. Its body marker disappea"
  },
  "messages": [
    {
      "id": "98045b52-a530-4a3a-8281-26af18dcea32",
      "author": {
        "name": "OpenGlance demo",
        "kind": "human"
      },
      "created_at": "2026-10-28T04:00:00Z",
      "body": "Confirmed: resolving saves locally and publication remains manual."
    }
  ]
}
-->
