---
title: Agent Context and Sync demo
type: feature-demo
status: maintained
source_repository: openglance/openglance
source_path: docs/user-guide.md
source_revision: 6f675a0
last_updated: 2026-09-06
ai_snippet: "[Demo] Select exact source-backed lines collect Agent Context locate document edits inspect local changes and publish deliberately"
---

# Agent Context and Sync

This page provides bounded passages for testing source-backed selection and a harmless local edit for
testing Sync.

## Passage A: product boundary

OpenGlance opens a local Git repository and presents it as a readable workspace. The repository remains
the shared source of truth. OpenGlance does not upload the content or create a separate hosted copy.

Select the two sentences above and confirm that copied context includes this file path and its exact
source lines.

## Passage B: human and agent interfaces

People use Preview, Live, and Source to read, inspect, and make focused edits. Agents and developers
work directly with the same repository through Git and their normal tools.

Add this passage to Agent Context together with Passage A. The collection should preserve the source of
each excerpt.

## Harmless Sync exercise

In Live, check the item and temporarily remove the word `local`, then return to Preview:

- [ ] Temporary local edit for the Sync demo.

Expected behavior:

1. automatic save writes the local Markdown file;
2. the edited line uses a warm highlight, and **Harmless Sync exercise** uses that color across the full
   document-navigation row while still jumping here;
3. the compact **Show deletions** control starts off; turning it on adds a small solid status dot and only
   a strikethrough to the read-only `local` text while leaving the existing current-document line numbers
   unchanged;
4. opening another document and returning restores the same cues;
5. Sync shows this file as unpublished, while publishing remains an explicit action;
6. undoing both edits returns the working tree to its previous content and clears the cues.

An edit before the first visible navigation heading would use the synthetic **Document start** row. The
in-document cues are intentionally lighter than a standard Git diff and do not stage or discard files.

Do not publish the practice edit unless you intentionally want to change the public demo.

## Describe a publication

Sync includes **Change summary (optional)** beside **Sync and publish**. Try entering
`Clarify the Sync exercise`, switch between Preview and Live, and confirm that the draft remains.
The first line becomes the commit title; additional lines become its body. A failed publication retains
the draft, and a successful publication clears it. **Sync and copy** uses the same summary.

Leaving the field blank generates a local description from change types and document titles. For an
existing document with `change_log.summary`, only values added or edited in the pending change are used.
Unchanged history, reordered entries, and date-only updates are not descriptions of the current edit.
New documents use their title because embedded history may have been copied. No AI service is required.
For this exercise, clear the draft and undo the practice edit when finished.

## Link handoff

An Open in OpenGlance link identifies a GitHub repository and a repository-relative Markdown or MDX
path. OpenGlance resolves that identity to a local checkout; the hosted page does not receive the
repository contents.

Return to the [demo index](../README.md).
