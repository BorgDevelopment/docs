# Odin Documentation

Documentation site for the [Odin](https://odin.borghq.io) security platform by Borg Security. Built with [Mintlify](https://mintlify.com).

## What's in here

- **Getting Started** — introduction to the Odin platform, quickstart guide
- **Platform** — findings, reports, and integrations (GitHub, Linear, Jira)
- **Mjolnir** — setup wizard, test users, code & documentation, domain verification

## Local development

Install the Mintlify CLI:

```bash
npm i -g mintlify
```

Then start the local preview server from the repo root:

```bash
npx mintlify dev
```

The site will be available at `http://localhost:3000`.

### Useful commands

| Command | What it does |
|---------|-------------|
| `npx mintlify dev` | Start local preview |
| `npx mintlify broken-links` | Check for broken internal links |
| `npx mintlify validate` | Validate the docs build |

## Project structure

```
docs/
├── getting-started/       # Introduction and quickstart
├── platform/              # Findings, reports, integrations
├── mjolnir/               # Mjolnir setup and configuration
│   ├── setup/             # Connect GitHub, scope, allowlisting
│   ├── test-users/        # Auth method guides
│   ├── code-and-docs/     # Repositories and file uploads
│   └── domain-verification/
├── images/                # Screenshots and assets
├── logo/                  # Brand logos (light/dark)
├── snippets/              # Reusable MDX snippets
└── docs.json              # Site configuration
```

## Adding content

1. Create or edit an `.mdx` file in the appropriate directory
2. Add YAML frontmatter with at least `title` and `description`
3. Add the page path to `docs.json` under the correct navigation group
4. Preview locally with `npx mintlify dev`

## Adding images

Place screenshots and diagrams in `images/` using the subdirectory that matches the section:

- `images/platform/` — platform features (findings, reports)
- `images/mjolnir/` — Mjolnir run dashboard, setup wizard
- `images/integrations/` — integration setup flows

Reference them in MDX with a `<Frame>` component:

```mdx
<Frame caption="Description of the screenshot">
  <img src="/images/platform/example.png" alt="Descriptive alt text" />
</Frame>
```

## Deployment

Changes pushed to the default branch are deployed automatically via the Mintlify GitHub app.

## Support

Reach out at [security@borgresearch.io](mailto:security@borgresearch.io).
