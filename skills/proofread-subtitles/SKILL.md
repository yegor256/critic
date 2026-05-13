---
name: proofread-subtitles
description: |
  Use this skill when proofreading a .srt subtitle file
  produced by Whisper or another voice-to-text engine.
  Fix punctuation, capitalization, sentence boundaries,
  and over-long lines, but leave timestamps, cue numbers,
  and the overall block structure untouched. Apply to
  English and Russian subtitles alike, and keep computer
  jargon in its conventional form.
  Use when user says "proofread subtitles", "fix the srt",
  "clean up whisper output", "punctuate subtitles", "fix
  captions", "subtitle proofreading", or attaches a `.srt`
  file for review.
---

Before editing the file, ask the author for a short list
  of domain-specific terms — proper nouns, product names,
  library and command names, technical jargon — that the
  voice-to-text engine is likely to mis-render, and use
  that list as the primary reference for spotting errors.

When the author declines to supply terms or asks to start
  immediately, proceed with the rules below and flag any
  cue whose correction was uncertain by its cue number so
  the author can review it afterwards.

Never modify timestamps, cue numbers, or the blank line
  between cues; the file comes from a voice-to-text engine
  whose timing is authoritative.

Never merge two cues into one or split one cue across two,
  even when the sentence boundary falls in the middle of a
  cue, because that would shift the timing.

Break any subtitle line longer than 42 characters into two
  lines inside the same cue, splitting at a clause boundary,
  a comma, or a conjunction so each line reads as a unit.

Keep at most two text lines per cue; if the text still does
  not fit after splitting, shorten wording rather than add a
  third line.

Add commas, periods, question marks, exclamation marks,
  colons, and semicolons where the spoken phrasing requires
  them, following standard punctuation rules of the source
  language.

Capitalize the first word of every sentence and every proper
  noun, even when Whisper produced lowercase output.

End every sentence with a terminal mark (`.`, `?`, or `!`),
  and start the next sentence with a capital letter, so each
  sentence has a visible beginning and end.

Fix obvious misrecognitions of common words and homophones
  (`there` versus `their`, `your` versus `you're`,
  `их` versus `и х`) when context makes the correct form
  unambiguous.

Preserve computer jargon in its conventional written form
  (`API`, `CLI`, `Git`, `Docker`, `JSON`, `HTTP`,
  `Kubernetes`); do not translate, expand, or localize it.

In Russian subtitles, write computer terms in English when
  that is the conventional form in Russian technical speech
  (`pull request`, not `пулл реквест`; `commit`, not
  `коммит`; `Git`, not `Гит`), but keep transliterations
  that are already standard in Russian usage.

Fix typos and spacing errors inside a line without rewording
  the sentence; the goal is proofreading, not rewriting.

Do not paraphrase, summarize, or polish the speaker's
  wording, even when the phrasing is awkward, repetitive,
  or grammatically loose, because the subtitles must match
  what was said.

Do not delete filler words (`uh`, `um`, `well`, `ну`,
  `вот`) unless the user asks for a clean transcript;
  Whisper usually drops them already.

Do not add speaker labels, sound descriptions, or
  bracketed annotations unless the source file already uses
  them.

Preserve the file's character encoding (UTF-8) and line
  endings; do not convert between CRLF and LF.

When unsure whether a change preserves the speaker's
  meaning, leave the original text and flag the cue number
  for the author to review.

Write the corrected output to a sibling file named
  `<original>-corrected.srt` rather than overwriting the
  source, so the author can diff the two versions before
  discarding the original.

After editing, verify that the number of cues, every cue
  number, and every timestamp line in the output match the
  source exactly; if any of these differ, the edit broke
  timing and must be redone before the file is delivered.

At the end of the run, report a short categorized summary
  of what was changed — punctuation, capitalization, jargon
  corrections, line splits, flagged cues — so the author
  can scan the edits without running a diff tool.
