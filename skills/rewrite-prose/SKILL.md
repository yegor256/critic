---
name: rewrite-prose
description: |
  Use this skill when the user wants to polish the wording of plain text
  documents and English embedded in source code, cutting filler and AI tells.
---

## Meaning

Preserve tone of voice.
Preserve meaning exactly.
Ask author when sentence is ambiguous.
Replace awkward constructions with cleaner ones of same meaning.

## Tense

Use present tense instead of `will`, except when future is point.

## Clichés

Cut clichés like `at the end of the day` or `needless to say`.
Cut `low-hanging fruit` and `circle back` too.
Cut tautologies like `end result`, `each and every`, or `free gift`.
Cut throat-clearing openers like `it is worth noting` or `here is the thing`.
Cut manufactured `not just X, but Y` contrast and state point directly.
Replace vague declarative like `the reasons are structural` with specifics.
Drop empty absolutes like `always` or `never` unless they hold literally.
Rewrite any sentence engineered to read like pull-quote.

## Lists

Use Oxford comma in lists of three or more.
Complete every list or name its category.
Drop trailing `etc.`, `and so on`, `and so forth`, or ellipses.

## Dashes

Separate two clauses with period or recast sentence rather than em dash.

## Voice

Prefer active voice unless actor is unknown or irrelevant.
Give every verb subject that can perform it.
Cut false agency where abstraction acts like person.
Name real actor in phrases like `the decision emerges`.

## Filler

Cut filler words like `very`, `really`, `just`, and `actually`.
Cut `basically` and `essentially` too.
Replace `very X` with stronger single word.
Replace `in order to` with `to`.

## Diction

Prefer Anglo-Saxon words over Latinate.
Use `use` instead of `utilize`, and `start` instead of `commence`.
Drop `that` when removal does not hurt readability.
Replace double negatives like `not uncommon` with positive word.

## Rhythm

Keep parallel grammar across list items.
Resist reflexive three-item rhythm when two items say enough.
Vary sentence length so rhythm never turns metronomic.
Split sentences carrying two ideas joined by `and` or `but`.

## Subjects

Lead with real subject instead of `there is` or `there are`, which delay it.

## Hedging

Cut hedging words like `perhaps`, `maybe`, `arguably`, and `sort of`.
Use them only when uncertainty is real.

## Layout

When writing for AI agents, place one thought per paragraph.
Headings carry no trailing period.
In Markdown, place URLs at bottom as reference definitions.
Use shortcut links in body text.

## Numbers

Spell numbers one through nine as words.
Write numbers from ten upward as digits.
Keep digits in tables, code, versions, and measurements.

## Restraint

Preserve author's vocabulary and stylistic choices.
Preserve quoted text, code, and proper names.
Preserve domain jargon that already follows its field's convention.
Make smallest change that fixes problem.

## Review

Show original next to non-trivial rewrite.
Ask author to confirm meaning survives.
Read result once and remove anything that still sounds machine-generated.

## Reflow

Reflow every touched sentence when file uses one-sentence-per-line layout.
Leave existing line breaks alone otherwise.

## Example

Polish this draft.

```text
At the end of the day, we utilized the system in order to basically improve things.
```

Return this version.

```text
We used the system to improve throughput.
```
