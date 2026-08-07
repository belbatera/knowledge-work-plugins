# Knowledge Work Plugins — Fork

[English](README.md) | [Português](README.pt-BR.md)

> **Fork notice.** This repository is a maintained fork of
> [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins),
> Anthropic's official collection of plugins that turn Claude into a specialist for your role, team,
> and company. It ships the same plugins and adds fixes and improvements to the bundled Zoom plugin —
> see the [Delta](#delta--what-this-fork-changes-vs-upstream) section. All credit for the collection
> goes to the upstream project.

Plugins that turn Claude into a specialist for your role, team, and company. Built for [Claude Cowork](https://claude.com/product/cowork), also compatible with [Claude Code](https://claude.com/product/claude-code).

## Delta — What This Fork Changes vs. Upstream

This fork improves the **Zoom plugin** (`partner-built/zoom-plugin`). Compared to upstream, **12 skill definition files** (`SKILL.md`) were changed, in two ways:

### 1. Skill identifier fix (12 skills)

The `name:` field in the frontmatter used path-style identifiers containing a slash (e.g. `contact-center/android`). Slash-based names are fragile — they can be interpreted as nested paths instead of flat skill identifiers, which breaks registration and namespacing. All 12 were renamed to flat, hyphenated identifiers (e.g. `contact-center-android`).

### 2. Skill definition refactor (6 skills)

Six of those files were also condensed from long, inline reference documents (97–1,019 lines) into focused skill definitions (41–59 lines). The skills now act as concise routing and decision guides that point to the dedicated reference docs shipped alongside them (`concepts/`, `examples/`, `references/`, `troubleshooting/`). Skills load faster, fire more reliably, and keep the deep detail one hop away.

| Skill | `name:` before | `name:` after | Scope |
|---|---|---|---|
| `contact-center/android` | `contact-center/android` | `contact-center-android` | Identifier fix |
| `contact-center/ios` | `contact-center/ios` | `contact-center-ios` | Identifier fix |
| `contact-center/web` | `contact-center/web` | `contact-center-web` | Identifier fix |
| `virtual-agent/android` | `virtual-agent/android` | `virtual-agent-android` | Identifier fix |
| `virtual-agent/ios` | `virtual-agent/ios` | `virtual-agent-ios` | Identifier fix |
| `virtual-agent/web` | `virtual-agent/web` | `virtual-agent-web` | Identifier fix |
| `meeting-sdk/linux` | `meeting-sdk/linux` | `meeting-sdk-linux` | Identifier fix + refactor (429 → 59 lines) |
| `ui-toolkit` | `ui-toolkit/web` | `ui-toolkit-web` | Identifier fix + refactor (555 → 45 lines) |
| `video-sdk/linux` | `video-sdk/linux` | `video-sdk-linux` | Identifier fix + refactor (443 → 42 lines) |
| `video-sdk/web` | `video-sdk/web` | `video-sdk-web` | Identifier fix + refactor (821 → 41 lines) |
| `video-sdk/windows` | `video-sdk/windows` | `video-sdk-windows` | Identifier fix + refactor (1,019 → 45 lines) |
| `zoom-mcp/whiteboard` | `zoom-mcp/whiteboard` | `zoom-mcp-whiteboard` | Identifier fix + refactor (97 → 54 lines) |

All changes are recorded in the fork's [commit history](https://github.com/belbatera/knowledge-work-plugins/commits/main) (latest: "Refactor zoom-mcp whiteboard skill documentation", `5113e9d`).

## Why Plugins

Cowork lets you set the goal and Claude delivers finished, professional work. Plugins let you go further: tell Claude how you like work done, which tools and data to pull from, how to handle critical workflows, and what slash commands to expose — so your team gets better and more consistent outcomes.

Each plugin bundles the skills, connectors, slash commands, and sub-agents for a specific job function. Out of the box, they give Claude a strong starting point for helping anyone in that role. The real power comes when you customize them for your company — your tools, your terminology, your processes — so Claude works like it was built for your team.

## Plugin Marketplace

We're open-sourcing 11 plugins built and inspired by our own work:

| Plugin | How it helps | Connectors |
|--------|-------------|------------|
| **[productivity](./productivity)** | Manage tasks, calendars, daily workflows, and personal context so you spend less time repeating yourself. | Slack, Notion, Asana, Linear, Jira, Monday, ClickUp, Microsoft 365 |
| **[sales](./sales)** | Research prospects, prep for calls, review your pipeline, draft outreach, and build competitive battlecards. | Slack, HubSpot, Close, Clay, ZoomInfo, Notion, Jira, Fireflies, Microsoft 365 |
| **[customer-support](./customer-support)** | Triage tickets, draft responses, package escalations, research customer context, and turn resolved issues into knowledge base articles. | Slack, Intercom, HubSpot, Guru, Jira, Notion, Microsoft 365 |
| **[product-management](./product-management)** | Write specs, plan roadmaps, synthesize user research, keep stakeholders updated, and track the competitive landscape. | Slack, Linear, Asana, Monday, ClickUp, Jira, Notion, Figma, Amplitude, Pendo, Intercom, Fireflies |
| **[marketing](./marketing)** | Draft content, plan campaigns, enforce brand voice, brief on competitors, and report on performance across channels. | Slack, Canva, Figma, HubSpot, Amplitude, Notion, Ahrefs, SimilarWeb, Klaviyo |
| **[legal](./legal)** | Review contracts, triage NDAs, navigate compliance, assess risk, prep for meetings, and draft templated responses. | Slack, Box, Egnyte, Jira, Microsoft 365 |
| **[finance](./finance)** | Prep journal entries, reconcile accounts, generate financial statements, analyze variances, manage close, and support audits. | Snowflake, Databricks, BigQuery, Slack, Microsoft 365 |
| **[data](./data)** | Query, visualize, and interpret datasets — write SQL, run statistical analysis, build dashboards, and validate your work before sharing. | Snowflake, Databricks, BigQuery, Definite, Hex, Amplitude, Jira |
| **[enterprise-search](./enterprise-search)** | Find anything across email, chat, docs, and wikis — one query across all your company's tools. | Slack, Notion, Guru, Jira, Asana, Microsoft 365 |
| **[bio-research](./bio-research)** | Connect to preclinical research tools and databases (literature search, genomics analysis, target prioritization) to accelerate early-stage life sciences R&D. | PubMed, BioRender, bioRxiv, ClinicalTrials.gov, ChEMBL, Synapse, Wiley, Owkin, Open Targets, Benchling |
| **[cowork-plugin-management](./cowork-plugin-management)** | Create new plugins or customize existing ones for your organization's specific tools and workflows. | — |

Install these directly from Cowork, browse the full collection here on GitHub, or build your own.

## Getting Started

### Quick Start

**Cowork** — install plugins from [claude.com/plugins](https://claude.com/plugins/).

**Claude Code** — add this fork as a marketplace, then install a plugin:

```bash
# Add the marketplace first (this fork)
claude plugin marketplace add belbatera/knowledge-work-plugins

# Then install a specific plugin (e.g. the Zoom plugin)
claude plugin install zoom-plugin@knowledge-work-plugins
```

Once installed, plugins activate automatically. Skills fire when relevant, and slash commands are available in your session (e.g., `/sales:call-prep`, `/data:write-query`).

### Step-by-Step for Beginners

1. **Install Claude Code** (or use [Claude Cowork](https://claude.com/product/cowork)) and sign in.
2. **Add the marketplace** from this fork:
   ```bash
   claude plugin marketplace add belbatera/knowledge-work-plugins
   ```
3. **Install a plugin** — replace `zoom-plugin` with any plugin name from the [marketplace table](#plugin-marketplace):
   ```bash
   claude plugin install zoom-plugin@knowledge-work-plugins
   ```
4. **Verify it works** — start a new session and ask something relevant to the plugin. Skills activate automatically when their triggers match; slash commands are available in your session.
5. **Customize it** — edit the plugin's `.mcp.json` (tool connections) and `skills/` files (domain knowledge) to match your tools and processes. See [Making Them Yours](#making-them-yours).
6. **Stay updated** — pull this repository or re-add the marketplace periodically to receive the latest fixes.

## How Plugins Work

Every plugin follows the same structure:

```
plugin-name/
├── .claude-plugin/plugin.json   # Manifest
├── .mcp.json                    # Tool connections
├── commands/                    # Slash commands you invoke explicitly
└── skills/                      # Domain knowledge Claude draws on automatically
```

- **Skills** encode the domain expertise, best practices, and step-by-step workflows Claude needs to give you useful help. Claude draws on them automatically when relevant.
- **Commands** are explicit actions you trigger (e.g., `/finance:reconciliation`, `/product-management:write-spec`).
- **Connectors** wire Claude to the external tools your role depends on — CRMs, project trackers, data warehouses, design tools, and more — via [MCP servers](https://modelcontextprotocol.io/).

Every component is file-based — markdown and JSON, no code, no infrastructure, no build steps.

## Making Them Yours

These plugins are generic starting points. They become much more useful when you customize them for how your company actually works:

- **Swap connectors** — Edit `.mcp.json` to point at your specific tool stack.
- **Add company context** — Drop your terminology, org structure, and processes into skill files so Claude understands your world.
- **Adjust workflows** — Modify skill instructions to match how your team actually does things, not how a textbook says to.
- **Build new plugins** — Use the `cowork-plugin-management` plugin or follow the structure above to create plugins for roles and workflows we haven't covered yet.

As your team builds and shares plugins, Claude becomes a cross-functional expert. The context you define gets baked into every relevant interaction, so leaders and admins can spend less time enforcing processes and more time improving them.

## Contributing

Plugins are just markdown files. Fork the repo, make your changes, and submit a PR to this repository. If your change is a general improvement to the collection (not a fork-specific fix), consider contributing it to the [upstream repository](https://github.com/anthropics/knowledge-work-plugins) as well.

## License

Distributed under the same license as the upstream project — see [`LICENSE`](LICENSE).
