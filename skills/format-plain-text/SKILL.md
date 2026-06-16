---
name: format-plain-text
description: |
  Use this skill when the user wants to format plain text documents
  with one sentence per line.
---

## Lines

Start every sentence on new line.
Break any sentence over 80 characters across lines.
Split at commas, conjunctions, or clause boundaries.
Use 100 characters as margin for `.tex` files.
Indent every continuation line by two spaces.

## Scope

Apply to Markdown body, TeX paragraphs, and `.txt` prose.
Apply to blockquotes and full-sentence list items too.

## Skip

Skip fenced code and inline code.
Skip YAML or TOML frontmatter, tables, headings, and link references.
Skip any line where hard break changes rendered output.

## Reflow

Preserve layout when document already follows these rules.
Reformat only sentences you touch when document does not follow them.
Reflow whole document only when asked.
