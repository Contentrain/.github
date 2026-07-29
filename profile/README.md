<div align="center">

<img src="https://contentrain.io/og-image.png" alt="Contentrain — Git-native content governance for AI-built products" width="880" />

### Govern the content your AI ships into code.

Contentrain turns hardcoded UI copy, docs, and structured content into a **Git-native system that AI agents can safely operate**.
Start locally with open-source MCP, CLI, and SDK packages. Add **Studio** when teams need review, roles, media, and delivery.

[Website](https://contentrain.io) · [Developer Docs](https://ai.contentrain.io) · [Studio Docs](https://docs.contentrain.io) · [Open Studio](https://studio.contentrain.io) · [Pricing](https://contentrain.io/pricing)

[![npm: @contentrain/mcp](https://img.shields.io/npm/v/%40contentrain%2Fmcp?label=%40contentrain%2Fmcp)](https://www.npmjs.com/package/@contentrain/mcp)
[![npm: contentrain](https://img.shields.io/npm/v/contentrain?label=contentrain)](https://www.npmjs.com/package/contentrain)
[![npm: @contentrain/query](https://img.shields.io/npm/v/%40contentrain%2Fquery?label=%40contentrain%2Fquery)](https://www.npmjs.com/package/@contentrain/query)
[![Packages: MIT](https://img.shields.io/badge/packages-MIT-blue)](https://github.com/Contentrain/ai/blob/main/LICENSE)
[![Studio: AGPL-3.0](https://img.shields.io/badge/Studio%20core-AGPL--3.0-blue)](https://github.com/Contentrain/studio/blob/main/LICENSE)
[![Discord](https://img.shields.io/badge/Discord-join-5865F2)](https://discord.gg/8XbFKfgeZx)

</div>

---

## Agent generates. Human approves. Git records every change.

Most teams don't wake up needing a CMS. They wake up with hardcoded copy spread across components, no translation path, and AI agents editing strings directly in source files.

Contentrain puts a governed content layer between the agent and your repository:

```
Agent decides  →  Contentrain enforces  →  Human reviews  →  Any platform consumes
(what content)    (schema, validation,      (branch, diff,     (JSON + Markdown,
                   canonical Git writes)     approval)          SDK, CDN, API)
```

The content contract never changes — only the surface you operate it from does.

## Try it in 30 seconds

```bash
npx contentrain init     # create the .contentrain/ workspace
npx contentrain serve    # open the local review UI
```

No account, no cloud, no proprietary content format. You now have models, validation, review branches, and a local UI.

## Two surfaces, one content contract

| | **Contentrain AI** | **Contentrain Studio** |
|---|---|---|
| **What it is** | Local-first, open-source operating core | Open-core team operations & delivery web app |
| **Who it's for** | Developers and AI coding agents | Editors, reviewers, and cross-functional teams |
| **Surface** | MCP, CLI, SDK, types, rules, skills | Chat, structured editing, review, media, CDN, APIs |
| **License** | MIT | AGPL-3.0 core + separately licensed enterprise modules |
| **Repo** | [`Contentrain/ai`](https://github.com/Contentrain/ai) | [`Contentrain/studio`](https://github.com/Contentrain/studio) |

Typical path: `contentrain init` → normalize hardcoded content → review branches → invite teammates into Studio → deliver through CDN/API when needed.

## Open-source packages

| Package | Role |
|---|---|
| [`@contentrain/mcp`](https://github.com/Contentrain/ai/tree/main/packages/mcp) | **24 MCP tools** over stdio or HTTP, with Local / GitHub / GitLab providers |
| [`contentrain`](https://github.com/Contentrain/ai/tree/main/packages/cli) | CLI, local Serve review UI, and MCP stdio entrypoint |
| [`@contentrain/query`](https://github.com/Contentrain/ai/tree/main/packages/sdk/js) | Generated, fully typed query SDK |
| [`@contentrain/types`](https://github.com/Contentrain/ai/tree/main/packages/types) | Shared type definitions and constants |
| [`@contentrain/rules`](https://github.com/Contentrain/ai/tree/main/packages/rules) | Agent quality rules and schema guardrails |
| [`@contentrain/skills`](https://github.com/Contentrain/ai/tree/main/packages/skills) | **15 Agent Skills** — workflow playbooks for AI agents |

MCP works with Claude Code, Claude Desktop, Cursor, Windsurf, Codex, and any MCP-compatible client.

## Normalize — the fastest way in

**Before** — copy is trapped in components. No structure, no locales, no review.

```tsx
<h1>Welcome to our platform</h1>
<p>Start your free trial today</p>
```

**After** — source uses keys, content lives in Git as structured, translatable data.

```tsx
<h1>{t('hero.title')}</h1>
<p>{t('hero.subtitle')}</p>
```

```json
// .contentrain/content/marketing/hero/en.json
{ "title": "Welcome to our platform", "subtitle": "Start your free trial today" }
```

Scan → extract → review. Source patching happens in a separate, reviewable phase.
→ [See the Normalize flow](https://contentrain.io/normalize)

## The content model

| Kind | Stores | Example |
|---|---|---|
| **Collection** | Multiple typed entries | Blog posts, products, team |
| **Singleton** | One entry per locale | Hero section, site config |
| **Document** | Markdown + frontmatter | Docs, articles, changelog |
| **Dictionary** | Flat key-value strings | i18n translations, UI labels |

**4 model kinds · 27 field types · locale-aware · canonical JSON + Markdown in Git.**

## Use your content anywhere

Content is plain JSON and Markdown — any language reads it directly. For TypeScript, generate a typed client:

```bash
npx contentrain generate
```

```ts
import { query, singleton, dictionary, document } from '#contentrain'

const hero    = singleton('hero').locale('en').get()
const posts   = query('blog-post').locale('en').include('author').all()
const labels  = dictionary('ui-labels').locale('tr').get('auth.login')
const article = document('docs').locale('en').bySlug('getting-started')
```

Works with Nuxt, Next.js, Astro, SvelteKit, Vue, React, Node, Go, Python, Swift, Flutter, and 20+ stacks.

## Starter templates

Production-ready repos with models, seed content, and a generated SDK client — click **Use this template** to start.

| Template | Framework | Use case |
|---|---|---|
| [astro-blog](https://github.com/Contentrain/contentrain-starter-astro-blog) | Astro | Blog / editorial |
| [astro-landing](https://github.com/Contentrain/contentrain-starter-astro-landing) | Astro | Landing page |
| [next-commerce](https://github.com/Contentrain/contentrain-starter-next-commerce) | Next.js | Commerce storytelling |
| [next-multi-surface-saas](https://github.com/Contentrain/contentrain-starter-next-multi-surface-saas) | Next.js | Marketing + app + docs |
| [next-saas-dashboard](https://github.com/Contentrain/contentrain-starter-next-saas-dashboard) | Next.js | SaaS dashboard copy |
| [next-white-label-portal](https://github.com/Contentrain/contentrain-starter-next-white-label-portal) | Next.js | White-label / multi-tenant |
| [nuxt-admin-console](https://github.com/Contentrain/contentrain-starter-nuxt-admin-console) | Nuxt | Admin console / operations |
| [nuxt-saas](https://github.com/Contentrain/contentrain-starter-nuxt-saas) | Nuxt | SaaS marketing site |
| [sveltekit-editorial](https://github.com/Contentrain/contentrain-starter-sveltekit-editorial) | SvelteKit | Editorial / publication |
| [vitepress-docs](https://github.com/Contentrain/contentrain-starter-vitepress-docs) | VitePress | Documentation site |

→ [Browse all templates](https://contentrain.io/templates)

## Editions

| Edition | Price | For |
|---|---|---|
| **Open source** | $0 · MIT packages | Local-first workflows, normalize, generated SDK, local review UI |
| **Starter** | $9/mo | Solo developers and small projects on Studio |
| **Pro** | $49/mo | Teams needing collaboration, higher limits, and API access |
| **Enterprise** | Custom | Self-managed licensing, SSO paths, custom limits, dedicated support |

The AGPL Studio core is also [self-hostable](https://contentrain.io/self-hosted) on infrastructure you control.
→ [See full pricing](https://contentrain.io/pricing)

## Who it's for

- **AI-native teams** — govern the copy your coding agents create instead of letting it scatter through source
- **Agencies** — one repeatable content workflow across every client project
- **Content teams** — editors change content without developers losing Git control
- **Platform teams** — one content contract for web, docs, mobile, and APIs

## Docs

- **[ai.contentrain.io](https://ai.contentrain.io)** — packages, MCP tools, CLI, SDK, and local workflows
- **[docs.contentrain.io](https://docs.contentrain.io)** — Studio guides, team workflows, self-hosting
- **[contentrain.io/playbooks](https://contentrain.io/playbooks)** — repeatable adoption workflows
- **[contentrain.io/security](https://contentrain.io/security)** — bounded agent operations and trust model

## Community

[Discord](https://discord.gg/8XbFKfgeZx) · [GitHub Discussions](https://github.com/Contentrain/ai/discussions) · [X / Twitter](https://x.com/Contentrain_io) · [LinkedIn](https://www.linkedin.com/company/contentrain) · [YouTube](https://www.youtube.com/@contentrain)

Contributions are welcome — see [CONTRIBUTING.md](https://github.com/Contentrain/ai/blob/main/CONTRIBUTING.md). If Contentrain is useful to you, a ⭐ on [`Contentrain/ai`](https://github.com/Contentrain/ai) helps others find it.

## Licensing

- **Packages** ([`Contentrain/ai`](https://github.com/Contentrain/ai)) — MIT
- **Studio core** ([`Contentrain/studio`](https://github.com/Contentrain/studio)) — AGPL-3.0, with separately licensed enterprise modules in `ee/`
