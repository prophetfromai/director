# Director

@/Users/qualitydrivensoftwareltd/git/claude.md/CLAUDE.md

## What This Is

This is the **command center**. Use this repo for high-level discussions, creating new product repos, and managing the portfolio. Every product repo is tracked in `repos.yaml` — that file is the single source of truth for what exists, where it lives, and what state it's in.

## Rules

- **All new repos are created programmatically** — never manually. Use the workflow below.
- **`repos.yaml` stays in sync** — every repo creation, archival, or status change updates it immediately.
- **Director never contains product code** — it's for orchestration and context only.
- **All product repos import the central brain** via `@import` in their CLAUDE.md (handled by the template).

## Creating a New Repo

When the user asks to create a new product/project:

1. Create the repo from the template:
   ```bash
   gh repo create prophetfromai/<name> --public --template prophetfromai/project-template --clone --clone-dir /Users/qualitydrivensoftwareltd/git/<name>
   ```
2. Fill in the `{placeholders}` in the new repo's `CLAUDE.md` — especially the **Summary** section (vision, scope, MVP, future direction). This is the single place any session or person goes to understand what the project is and where it's heading.
3. Add the repo to `repos.yaml` in this director repo
4. Commit and push both the new repo and this director repo

## Organizational Scheme

Repos are categorised in `repos.yaml` by **type** and **status**:

**Types:**
- `product` — revenue-generating, user-facing applications
- `tool` — internal tools (may graduate to product)
- `infrastructure` — meta repos: knowledge base, templates, pipelines
- `client` — one-off work for specific clients
- `experiment` — prototypes, spikes, throwaway explorations

**Statuses:**
- `active` — in development or live
- `paused` — on hold, may resume
- `archived` — no longer maintained

## Monologue

`monologue.md` is the **portfolio-level** log — cross-product ideas, strategic direction, and themes that don't belong to a single repo. Scan it before any strategic discussion or new product idea. See `topics/conventions/` in the central repo for the full protocol.

## Reading repos.yaml

Before any discussion about the portfolio, repo organisation, or creating something new — read `repos.yaml` first for current state.
