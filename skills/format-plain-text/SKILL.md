---
name: format-plain-text
description: |
  Use this skill to format plain text documents with one sentence per line.
---

Start every sentence on a new line.
Break any sentence over 80 characters across lines, splitting at commas, conjunctions, or clause boundaries.
Use 100 characters as the margin for `.tex` files.
Indent every continuation line by two spaces.
Apply to Markdown body, TeX paragraphs, `.txt` prose, blockquotes, and full-sentence list items.
Skip fenced code, inline code, YAML or TOML frontmatter, tables, headings, link references, or any line where a hard break changes rendered output.
Preserve layout when a document already follows these rules.
Reformat only the sentences you touch when a document does not follow them, unless asked for a full reflow.
