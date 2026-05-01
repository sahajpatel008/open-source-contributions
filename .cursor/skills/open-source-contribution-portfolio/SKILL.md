---
name: open-source-contribution-portfolio
description: Organize an open source contribution portfolio and turn issues, PRs, commits, Bugzilla tickets, or review pages into recruiter-friendly and engineer-friendly case studies. Use when documenting open source contributions, updating contribution category indexes, writing portfolio README entries, or classifying work as bug fixes, features, documentation, tests, performance, or tooling.
---

# Open Source Contribution Portfolio

## Purpose

Use this skill to document open source contributions in a pinned portfolio repository. The goal is to make each contribution easy for recruiters to scan and credible for engineers to inspect.

Write like a portfolio maintainer: concise, accurate, evidence-backed, and honest about the type of work.

## Repository Shape

Prefer this structure:

```text
README.md
contributions/
  README.md
  _template.md
  project-name-contribution-title.md
categories/
  bug-fixes.md
  features.md
  documentation.md
  tests.md
  performance.md
  tooling-devex.md
assets/
  screenshots/
```

If the repo already has a structure, follow it unless it is clearly missing a portfolio index, contribution writeups, or category pages.

## Workflow

1. Gather evidence before writing:
   - Read the provided issue, PR, commit, review, Bugzilla ticket, release note, or uploaded export.
   - Capture project name, contribution title, status, author/assignee, reviewer/mentor if useful, merged commit, changed files, tests, milestone/release, and user impact.
   - Prefer official links: upstream issue, PR/review, commit, release note, docs page, or bug tracker.

2. Classify the contribution:
   - `bug-fixes.md`: broken behavior, regression, incorrect output, crash, error, or edge case fix.
   - `features.md`: new capability, enhancement, UX improvement, or expanded behavior.
   - `documentation.md`: docs, examples, guides, setup instructions, API references.
   - `tests.md`: regression tests, new test coverage, reliability improvements.
   - `performance.md`: speed, memory, bundle size, build time, query/runtime efficiency.
   - `tooling-devex.md`: CI, local setup, linting, formatting, build tooling, contributor workflow.
   - A contribution may appear in multiple categories when each category reflects real work.
   - Do not call something a bug fix only because it came from a bug tracker. Use the issue type and actual behavior change.

3. Update the main `README.md`:
   - Add the contribution to `Highlights` if it is notable or recent.
   - Add or update a `Featured Contributions` entry for strong work.
   - Keep recruiter-facing text short and impact-focused.
   - Include links to the detailed writeup and official upstream evidence.

4. Create or update a detailed writeup in `contributions/`:
   - Use one file per meaningful contribution.
   - Use lowercase descriptive file names, for example `firefox-translations-default-target-language.md`.
   - Explain the problem, solution, technical details, tests, impact, and skills demonstrated.
   - Mention files changed only when they help engineers evaluate the work.

5. Update category pages:
   - Add one table row to every relevant category.
   - Keep rows concise: project, contribution, status, impact, links.
   - Replace placeholder rows like `Coming soon` once real contributions exist.

6. Verify:
   - Check Markdown formatting and relative links.
   - Run available diagnostics or linters if the environment supports them.
   - Do not invent PRs, metrics, release versions, or impact claims. If a detail is unknown, omit it or mark it as unknown.

## Main README Entry Format

Use this highlight row format:

```markdown
| Project | Contribution | Type | Impact | Links |
| --- | --- | --- | --- | --- |
| Firefox | Suggested the default target language after changing the detected source language in Firefox Translations | Feature / UX / Tests | Reduced a repeated manual step in the full-page translation flow; fixed in Firefox 152 | [Writeup](contributions/firefox-translations-default-target-language.md) / [Bug](https://bugzilla.mozilla.org/show_bug.cgi?id=2031015) / [Commit](https://github.com/mozilla-firefox/firefox/commit/242c60757e03) |
```

Use this featured contribution format:

```markdown
### Contribution Title

- **Project:** Project name
- **Repository:** Link to repository
- **Issue / Bug / PR:** Official upstream link
- **Commit:** Merged commit, if available
- **Status:** Draft / Open / Merged / RESOLVED FIXED / Closed
- **Type:** Bug fix / Feature / Documentation / Tests / Performance / Tooling
- **Tech Stack:** Languages, frameworks, tools
- **Summary:** One or two sentences explaining what changed.
- **Impact:** One sentence explaining why the contribution mattered.
```

## Contribution Writeup Template

```markdown
# Project Name - Contribution Title

## Links

- **Repository:**
- **Issue / Bug / PR:**
- **Commit:**
- **Status:**

## Summary

Briefly explain the contribution in 2-4 sentences. If it was the author's first open source contribution, mention that only when true and relevant.

## Problem

Describe the bug, missing behavior, unclear documentation, performance issue, or developer experience problem.

## Solution

Explain the implementation approach, tradeoffs, and constraints.

## Technical Details

- **Languages / Frameworks:**
- **Files changed:**
- **Tests added or updated:**
- **Edge cases handled:**

## Impact

Explain the user, maintainer, or developer impact. Be specific and avoid unsupported metrics.

## Skills Demonstrated

- Reading unfamiliar codebases
- Debugging
- Writing tests
- API or UI design
- Documentation
- Maintainer communication

## Notes

Add review context, mentor feedback, screenshots, or follow-up work when useful.
```

## Writing Rules

- Be accurate before being impressive.
- Prefer "enhancement" or "UX improvement" when the source issue is not actually a defect.
- Include testing work when the commit includes tests, even if the primary category is a feature or bug fix.
- Use official project terminology from the upstream issue or codebase.
- Keep recruiter-facing sections skimmable and engineer-facing writeups specific.
- Avoid filler like "worked on" or "helped with"; say what changed and why it mattered.
- Never fabricate impact. A modest verified impact is better than a broad unsupported claim.
