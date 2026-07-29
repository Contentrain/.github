---
title: Contentrain
homepage: https://contentrain.io/
twitter: contentrain_io
opensource: "Yes"
license: "MIT (packages) / AGPL-3.0 (Studio core)"
typeofcms: "Git-based"
supportedgenerators:
  - NuxtJs
  - NextJs
  - Astro
  - SvelteKit
  - Remix
  - VitePress
  - Docusaurus
  - Hugo
  - Jekyll
  - 11ty
  - Gatsby
  - React
  - Vue
  - Svelte
  - Angular
  - All
description: Contentrain is Git-native content governance for AI-built products. Open-source MCP, CLI, and SDK packages let AI agents extract and operate structured content in Git; Studio adds team review, roles, media, and delivery.
---

# Contentrain — organization meta

This repository holds GitHub organization-level defaults for [@Contentrain](https://github.com/Contentrain).

- [`profile/README.md`](profile/README.md) — the public organization profile page rendered at [github.com/Contentrain](https://github.com/Contentrain)

## About Contentrain

**Govern the content your AI ships into code.**

Contentrain turns hardcoded UI copy, docs, and structured content into a Git-native system that AI agents can safely operate. Agents generate, humans approve, and Git records every change.

Two surfaces, one content contract:

| Surface | Repo | License | What it does |
|---|---|---|---|
| **Contentrain AI** | [`Contentrain/ai`](https://github.com/Contentrain/ai) | MIT | Local-first operating core — 24 MCP tools, CLI, typed query SDK, agent rules and skills |
| **Contentrain Studio** | [`Contentrain/studio`](https://github.com/Contentrain/studio) | AGPL-3.0 core | Team operations and delivery — chat, structured editing, review, media, CDN, APIs |

```bash
npx contentrain init     # create the .contentrain/ workspace
npx contentrain serve    # open the local review UI
```

Content lives in your repository as canonical JSON and Markdown across 4 model kinds and 27 field types — no proprietary format, no vendor runtime.

## Links

- [contentrain.io](https://contentrain.io) — website
- [ai.contentrain.io](https://ai.contentrain.io) — developer docs (packages, MCP, CLI, SDK)
- [docs.contentrain.io](https://docs.contentrain.io) — Studio docs (team workflows, self-hosting)
- [studio.contentrain.io](https://studio.contentrain.io) — Studio app
- [Discord](https://discord.gg/8XbFKfgeZx) · [X](https://x.com/Contentrain_io) · [LinkedIn](https://www.linkedin.com/company/contentrain) · [YouTube](https://www.youtube.com/@contentrain)
