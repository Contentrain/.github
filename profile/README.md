<div align="center">

<img src="https://raw.githubusercontent.com/Contentrain/.github/main/profile/cover.png" alt="Contentrain — content governance for teams and AI agents" width="880" />

### Govern the content your AI ships into code.

Contentrain is a **content governance ecosystem for teams and AI agents**. Content lives in Git as structured JSON and Markdown.
Start locally with the open-source MCP, CLI, and SDK packages. Add **Studio** when teams need review, roles, media, and delivery.
Moving off WordPress? **Bridge** exports your content for free, and **Migrate** moves the whole site to Astro.

[Website](https://contentrain.io) · [Developer Docs](https://ai.contentrain.io) · [Studio Docs](https://docs.contentrain.io) · [Open Studio](https://studio.contentrain.io) · [Migrate](https://migrate.contentrain.io) · [Bridge](https://wordpress.org/plugins/contentrain-bridge/) · [Pricing](https://contentrain.io/pricing)

[![npm: @contentrain/mcp](https://img.shields.io/npm/v/%40contentrain%2Fmcp?label=%40contentrain%2Fmcp)](https://www.npmjs.com/package/@contentrain/mcp)
[![npm: contentrain](https://img.shields.io/npm/v/contentrain?label=contentrain)](https://www.npmjs.com/package/contentrain)
[![npm: @contentrain/query](https://img.shields.io/npm/v/%40contentrain%2Fquery?label=%40contentrain%2Fquery)](https://www.npmjs.com/package/@contentrain/query)
[![Packages: MIT](https://img.shields.io/badge/packages-MIT-blue)](https://github.com/Contentrain/ai/blob/main/LICENSE)
[![Studio: AGPL-3.0](https://img.shields.io/badge/Studio%20core-AGPL--3.0-blue)](https://github.com/Contentrain/studio/blob/main/LICENSE)
[![Discord](https://img.shields.io/badge/Discord-join-5865F2)](https://discord.gg/8XbFKfgeZx)

</div>

---

## Agent generates. Human approves. Git records every change.

Most teams don't wake up needing a new content platform. They wake up with hardcoded copy spread across components, no translation path, and AI agents editing strings directly in source files.

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

## Four parts, one content contract

| | **Open-source tools** | **Studio** | **Migrate** | **Bridge** |
|---|---|---|---|---|
| **What it is** | Local-first packages for developers and agents | Team operating surface for governed content | Service that moves a WordPress site to Astro | Free WordPress plugin |
| **Who it's for** | Developers and AI coding agents | Editors, reviewers, and cross-functional teams | WordPress site owners leaving WordPress | WordPress sites that want their content in Git |
| **What you get** | MCP, CLI, SDK, types, rules, skills | Chat, structured editing, review, roles, media, CDN, APIs | An Astro project with its content and template structure, delivered to your GitHub or as a ZIP | Content and interface text as a validated Contentrain store, as a ZIP or to your GitHub |
| **License** | MIT | AGPL-3.0 core + separately licensed `ee/` | Paid service | GPL-2.0-or-later |
| **Where** | [`Contentrain/ai`](https://github.com/Contentrain/ai) | [`Contentrain/studio`](https://github.com/Contentrain/studio) | [migrate.contentrain.io](https://migrate.contentrain.io) | [`Contentrain/wordpress-bridge`](https://github.com/Contentrain/wordpress-bridge) · [WordPress.org](https://wordpress.org/plugins/contentrain-bridge/) |

Typical path: `contentrain init` → normalize hardcoded content → review branches → invite teammates into Studio → deliver through CDN/API when needed.

## Open-source packages

| Package | Role |
|---|---|
| [`@contentrain/mcp`](https://github.com/Contentrain/ai/tree/main/packages/mcp) | **27 MCP tools** over stdio or HTTP, with Local / GitHub / GitLab providers (the 5 media tools need a provider with a media stack, such as Studio) |
| [`contentrain`](https://github.com/Contentrain/ai/tree/main/packages/cli) | CLI, local Serve review UI, and MCP stdio entrypoint |
| [`@contentrain/query`](https://github.com/Contentrain/ai/tree/main/packages/sdk/js) | Generated, fully typed query SDK |
| [`@contentrain/types`](https://github.com/Contentrain/ai/tree/main/packages/types) | Shared type definitions and constants |
| [`@contentrain/rules`](https://github.com/Contentrain/ai/tree/main/packages/rules) | Agent quality rules and schema guardrails |
| [`@contentrain/wp-import`](https://github.com/Contentrain/ai/tree/main/packages/wp-import) | WordPress content into a Contentrain store (`contentrain import`) |
| [`@contentrain/skills`](https://github.com/Contentrain/ai/tree/main/packages/skills) | **16 Agent Skills** — workflow playbooks for AI agents |

MCP works with Claude Code, Claude Desktop, Cursor, Windsurf, Codex, and any MCP-compatible client.

No local server to run? [MCP Cloud](https://docs.contentrain.io/developer/mcp-cloud) is Studio's hosted MCP endpoint: an agent connects over HTTP with a project key, with no checkout and no MCP server of its own.

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

`contentrain init` recognizes 29 stacks, from Nuxt, Next.js, Astro, and SvelteKit to Django, Rails, Laravel, Go, and Flutter. Any language that reads JSON and Markdown can read the content.

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
- **WordPress sites** — export content with Bridge, or move the whole site to Astro with Migrate
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
- **Bridge** ([`Contentrain/wordpress-bridge`](https://github.com/Contentrain/wordpress-bridge)) — GPL-2.0-or-later
- **Migrate** ([migrate.contentrain.io](https://migrate.contentrain.io)) — paid service
