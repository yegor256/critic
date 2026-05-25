---
name: proofread-subtitles
description: |
  Use this skill to proofread a `.srt` subtitle file produced
  by Whisper or another voice-to-text engine.
---

Ask the author for domain-specific terms the engine likely misrenders.
Use that list as the primary reference for errors.
Proceed without the list when the author declines.
Flag uncertain cues by number instead.
Never modify timestamps, cue numbers, or the blank line between cues.
Never merge two cues or split one cue across two.
Break any line over 42 characters into two within the same cue.
Split at a clause boundary, comma, or conjunction.
Allow at most two text lines per cue.
Shorten wording rather than add a third line.
Add punctuation where spoken phrasing requires it.
Follow the source language's rules.
Capitalize the first word of every sentence and every proper noun.
End every sentence with a terminal mark.
Fix obvious homophone and word misrecognitions when context is unambiguous.
Preserve computer jargon in its conventional form.
Use `API`, `CLI`, `Git`, `Docker`, `JSON`, `HTTP`, and `Kubernetes` as written.
In Russian subtitles, write computer terms in English.
Follow the conventions of Russian tech speech.
Write `pull request` instead of `пулл реквест`.
Keep transliterations already standard in Russian.
Fix typos and spacing errors without rewording the sentence.
Do not paraphrase, summarize, or polish the speaker's wording.
Do not delete filler words like `uh`, `um`, `well`, `ну`, or `вот`.
Delete them only when asked for a clean transcript.
Do not add speaker labels or sound descriptions.
Do not add bracketed annotations unless the source already uses them.
Preserve the file's UTF-8 encoding and line endings.
Leave the original when unsure a change preserves meaning.
Flag the cue number instead.
Write the output to a sibling file `<original>-corrected.srt`.
Never overwrite the source.
Verify the cue count matches the source.
Verify every cue number and timestamp matches too.
Report a short categorized summary of changes at the end.
