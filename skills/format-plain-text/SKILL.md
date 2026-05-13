---
name: format-plain-text
description: |
  Use this skill whenever creating or editing plain
  text documents — Markdown (.md), TeX (.tex), or .txt files.
  Apply the three rules below to every sentence: one sentence per line,
  wrap long sentences across multiple lines, and indent continuation
  lines by two spaces. Do NOT apply to source code files, code
  blocks inside Markdown, YAML, JSON, or any file where
  line breaks change meaning.
---

Start every sentence on a new line, even when sentences are
  short.

Break any sentence wider than 80 characters across multiple
  lines, splitting at commas, conjunctions, or clause
  boundaries (keep the margin at 100 characters for .tex files).

Indent every continuation line by exactly two spaces beyond
  the surrounding context, so the reader can tell a wrapped
  line from a new sentence.

Apply these rules to Markdown body text, TeX paragraphs,
  `.txt` prose, blockquotes, and full-sentence list items.

Do not apply them to fenced code, inline code, YAML or TOML
  frontmatter, tables, headings, link references, or any
  line where a hard break would change rendered output.

When editing a document that already follows these rules,
  preserve the layout and apply the rules to anything you
  rewrite.

When editing a document that does not follow them, reformat
  only the sentences you touch unless the user asks for a
  full reflow.
