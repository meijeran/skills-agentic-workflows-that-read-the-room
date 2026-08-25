---
name: update-github-info
description: Keep Mona's GitHub information page current from official GitHub sources.
on:
  schedule: daily
  workflow_dispatch:

permissions:
  contents: read
  pull-requests: read
  issues: read

tools:
  github:
  edit:
  web-fetch:

network:
  allowed:
    - github.blog
    - github.com
    - awesome-copilot.github.com

safe-outputs:
  create-pull-request:
    draft: true
    title-prefix: "[mona]"
---

Read `notes/mona-notes.md` before making any changes.

Use the web-fetch tool to read these official sources:

- https://github.blog/latest/
- https://github.blog/changelog/
- https://awesome-copilot.github.com/workflows/

Identify concise, practical updates that help developers learn GitHub faster. Mention the source whenever an update comes from the GitHub Blog, GitHub Changelog, or Awesome Copilot workflows. Update `site/content/github-info.md` with relevant findings, preserving the existing style and structure.

Use the safe output `create-pull-request` to propose the changes. Do not write directly to `main`. Open a pull request containing the update for Mona to review.
