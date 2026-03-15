# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Documentation site for the **Odin** security platform by Borg Security. Built with [Mintlify](https://mintlify.com). Content is MDX files with YAML frontmatter; site configuration lives in `docs.json`.

## Common Commands

| Command | Purpose |
|---------|---------|
| `npx mintlify dev` | Start local preview at localhost:3000 |
| `npx mintlify broken-links` | Check for broken internal links |
| `npx mintlify validate` | Validate the docs build |

There is no package.json, test suite, or build step — this is a pure Mintlify docs repo.

## Architecture

- **`docs.json`** — Single source of truth for site config: navigation (tabs → groups → pages), theme, colors, navbar, footer, anchors. Two top-level tabs: "Getting Started" and "Mjolnir".
- **`getting-started/`** — Introduction and quickstart guides.
- **`platform/`** — Findings, reports, and integrations (GitHub, Linear, Jira).
- **`mjolnir/`** — Setup, test users (multiple auth methods), code & docs, domain verification. This is the largest content area.
- **`snippets/`** — Reusable MDX snippets imported across pages.
- **`images/`** — Screenshots organized by section (`platform/`, `mjolnir/`, `integrations/`).
- **`.mintignore`** — Excludes `drafts/` and `*.draft.mdx` from builds.

## Content Conventions

- Every `.mdx` file needs at minimum `title` in its YAML frontmatter; include `description` for SEO.
- When creating a new page, **always add it to `docs.json` navigation** or it won't appear in the sidebar.
- Internal links use root-relative paths without file extensions: `/getting-started/quickstart`.
- Images go in `images/` under the matching section subdirectory and are referenced with `<Frame>` components.
- Code blocks must have language tags. All images must have alt text.
- Use `docs.json` (never `mint.json` which is deprecated).

## Deployment

Changes pushed to the default branch (`main`) deploy automatically via the Mintlify GitHub app.

## Mintlify Skill

This repo has a Mintlify skill at `.agents/skills/mintlify/SKILL.md` with detailed component guidance, writing standards, and workflow checklists. Consult it when doing significant content work.
