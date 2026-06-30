---
name: proofread-subtitles
description: |
  Use this skill when the user wants to proofread a `.srt` subtitle file
  produced by Whisper or another voice-to-text engine.
---

## Reference

Ask author for domain-specific terms engine likely misrenders.
Use that list as primary reference for errors.
Proceed without list when author declines.
Flag uncertain cues by number instead.

## Structure

Keep timestamps, cue numbers, and blank line between cues unchanged.
Keep each cue's boundaries exactly as in source.
Break any line over 42 characters into two within same cue.
Split at clause boundary, comma, or conjunction.
Allow at most two text lines per cue.
Shorten wording rather than add third line.

## Punctuation

Add punctuation where spoken phrasing requires it.
Follow source language's rules.
Capitalize first word of every sentence and every proper noun.
End every sentence with terminal mark.

## Corrections

Fix obvious homophone and word misrecognitions when context is unambiguous.
Preserve computer jargon in its conventional form.
Use `API`, `CLI`, `Git`, `Docker`, `JSON`, `HTTP`, and `Kubernetes` as written.
Fix typos and spacing errors without rewording sentence.

## Russian

In Russian subtitles, write computer terms in English.
Follow conventions of Russian tech speech.
Write `pull request` instead of `пулл реквест`.
Keep transliterations already standard in Russian.

## Preserve

Preserve speaker's word choice and phrasing.
Keep filler words like `uh`, `um`, `well`, `ну`, and `вот`.
Delete them only when author requests filler-free transcript.
Omit speaker labels and sound descriptions.
Add bracketed annotations only where source already uses them.
Preserve file's existing encoding and line endings.

## Uncertain

Leave original when unsure change preserves meaning.
Flag cue number instead.

## Output

Write output to sibling file `<original>-corrected.srt`.
Keep source file intact.
Verify cue count matches source.
Verify every cue number and timestamp matches too.
Report short categorized summary of changes at end.

## Example

Correct this raw cue.

```text
1
00:00:01,000 --> 00:00:03,000
lets push this to git hub tomorrow
```

Return this cue.

```text
1
00:00:01,000 --> 00:00:03,000
Let's push this to GitHub tomorrow.
```
