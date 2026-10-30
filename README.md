---
title: Contentrain
homepage: https://contentrain.io/
twitter: contentrain_io
opensource: "Yes"
license: "MIT (packages) / AGPL-3.0 (Studio core)"
typeofcms: "Git-based"
supportedgenerators:
  - Nuxt
  - Next.js
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
description: Contentrain is a content governance ecosystem for teams and AI agents. Open-source MCP, CLI, and SDK packages let AI agents extract and operate structured content in Git; Studio adds team review, roles, media, and delivery; Bridge and Migrate bring WordPress sites in.
---

# Contentrain — organization meta

This repository holds GitHub organization-level defaults for [@Contentrain](https://github.com/Contentrain).

- [`profile/README.md`](profile/README.md) — the public organization profile page rendered at [github.com/Contentrain](https://github.com/Contentrain)

## About Contentrain

**Govern the content your AI ships into code.**

Contentrain is a content governance ecosystem for teams and AI agents. It turns hardcoded UI copy, docs, and structured content into a Git-native system that AI agents can safely operate. Agents generate, humans approve, and Git records every change.

Four parts, one content contract:

| Surface | Repo | License | What it does |
|---|---|---|---|
| **Open-source tools** | [`Contentrain/ai`](https://github.com/Contentrain/ai) | MIT | Local-first packages — 27 MCP tools, CLI, typed query SDK, agent rules and skills |
| **Studio** | [`Contentrain/studio`](https://github.com/Contentrain/studio) | AGPL-3.0 core | Team operating surface — chat, structured editing, review, roles, media, CDN, APIs |
| **Migrate** | [migrate.contentrain.io](https://migrate.contentrain.io) | Paid service | Moves a WordPress site to Astro, with its content and template structure |
| **Bridge** | [`Contentrain/wordpress-bridge`](https://github.com/Contentrain/wordpress-bridge) | GPL-2.0-or-later | Free WordPress plugin — exports content as a Contentrain store, as a ZIP or to your GitHub |

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
