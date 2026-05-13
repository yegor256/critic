<!--
SPDX-FileCopyrightText: Copyright (c) 2026 Yegor Bugayenko
SPDX-License-Identifier: MIT
-->

# Quality Control in Software Projects

Quality is non-negotiable.
Yet most teams delegate the responsibility for it to the same
  programmers who are paid to ship features quickly, which produces
  a conflict of interest the project rarely wins.
Quality must be enforced by infrastructure, not by goodwill.

## Introduction

Speed and quality pull in opposite directions.
A programmer paid to close tickets has every reason to cut corners,
  and a programmer paid to maintain quality has every reason to slow
  down.
When the same person is asked to do both, one of the two goals
  always loses.

The mistake is asking.

A mature project does not ask programmers to police themselves.
It builds the rules into the pipeline, the repository, and the
  review process, so low-quality work cannot enter the codebase
  even when someone tries to push it through.
Tools like [GitHub Actions], [Jenkins], and [SonarQube] exist
  precisely so the rules can hold without human judgement.

## The Programmer's Incentive

Programmers ship.
That is the work.

A team that rewards velocity should not be surprised when its
  members optimise for velocity, including by skipping tests,
  ignoring lint warnings, and merging without review.
Asking them to defend quality on top of shipping is asking them
  to fight their own paycheque.

## The Infrastructure's Job

Quality belongs to the infrastructure.
The build system, the version control rules, and the review
  pipeline must reject bad work without human judgement.

The minimum bar for a serious project includes:

- A read-only master branch that accepts only merged pull requests.
- A pre-merge build that runs every test, every linter, and every
  static analyzer.
- Coverage thresholds that fail the build when they slip.
- At least two independent reviewers on every change.
- A rule that no one merges their own code, ever.

None of these rules trust the author of the change.
Each of them assumes the author will, at some point, try to slip
  something through, and each closes one route by which they
  could succeed.

## A Concrete Example

Suppose the build invokes the linter through a wrapper script.
The wrapper must fail the build on any warning, not just on
  errors, because a warning today is an error tomorrow.

```bash
$ ./scripts/lint.sh --fail-on-warning --report=junit --output=build/lint-report.xml
```

A line like that one is ugly to read but trivial to enforce, and
  enforcement is the point.
The build either passes or it does not.
No human reads the output and decides whether the warning matters.

## The Caveat

This model only works in projects mature enough to honour it.
A team that disables the linter under deadline pressure has no
  infrastructure, only the appearance of one.
Worse, a team that allows "temporary" bypasses creates a folklore
  in which every bypass is temporary and none are ever removed.

The discipline is binary.
Either the rules hold for everyone, every time, or they do not
  exist.

## Conclusion

Programmers should be fast.
Infrastructure should be strict.
When those two forces are aligned against each other, the project
  ships quickly without losing the quality it cannot afford to lose.

[GitHub Actions]: https://github.com/features/actions
[Jenkins]: https://www.jenkins.io
[SonarQube]: https://www.sonarsource.com/products/sonarqube/
