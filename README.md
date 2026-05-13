# Critic

[![License](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/yegor256/critic/blob/master/LICENSES/MIT.txt)

Skills for an AI critic that helps writing and proofreading texts.

The bundle ships four skills, each focused on a single editing task:

* [`analyze-argumentation-flow`](skills/analyze-argumentation-flow/SKILL.md)
  — diagnose flaws in an argument without rewriting the prose.
* [`format-plain-text`](skills/format-plain-text/SKILL.md)
  — enforce one sentence per line and indented continuations
    in Markdown, TeX, and `.txt`.
* [`proofread-subtitles`](skills/proofread-subtitles/SKILL.md)
  — fix punctuation, capitalization, and line length in `.srt`
    files produced by Whisper or similar engines.
* [`rewrite-prose`](skills/rewrite-prose/SKILL.md)
  — tighten wording, cut filler, and fix grammar without
    changing the author's voice.

Suppose you write with [Claude Code].
You do not need to clone this repository — install the bundle as a
  plugin straight from GitHub.
Inside a Claude Code session, run:

```text
/plugin marketplace add yegor256/plugins
/plugin install critic@yegor256
```

The first command registers the [yegor256/plugins] marketplace,
  which lists every plugin maintained under the `yegor256` account;
  the second installs the `critic` plugin from it,
  which exposes every skill under `skills/` to your sessions
  automatically.

To update later, run `/plugin marketplace update yegor256`;
  to remove, run `/plugin uninstall critic@yegor256`.

[yegor256/plugins]: https://github.com/yegor256/plugins

[Claude Code]: https://code.claude.com/docs/en/skills
