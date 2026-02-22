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
2. Fill in the `{placeholders}` in the new repo's `CLAUDE.md`
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

Every repo has its own `monologue.md`. Director's is the **portfolio-level** one — cross-product ideas, new product thoughts, strategic direction, and themes that don't belong to a single repo.

**Reading:** Scan `monologue.md` before any strategic discussion, new product idea, or portfolio-level decision. It's cheap context.

**Writing:** When someone raises an idea, changes direction, or expresses intent — append a one-liner to the top of the log:
```
- [YYYY-MM-DD] Name: the gist in very few words — related product/idea
```

Don't over-document. Only capture signal: new ideas, shifts in direction, recurring themes, or decisions. Skip routine implementation chatter.

## Reading repos.yaml

Before any discussion about the portfolio, repo organisation, or creating something new — read `repos.yaml` first for current state.
