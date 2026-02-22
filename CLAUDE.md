# Quartz Blog — wiasliaw.io

## Project Overview

This is a [Quartz v4](https://quartz.jzhao.xyz) static site generator for a personal blog, deployed to **Cloudflare Pages**. Blog content lives in a separate git submodule (`content/` → `wiasliaw/blog-content`) and is not part of this repository.

## Upstream Sync Policy

This repo **regularly syncs with upstream** `jackyzha0/quartz` (branch `v4`). All changes must be upstream-compatible to avoid merge conflicts.

### Safe to Edit (user-owned files)

- `quartz.config.ts` — site configuration, theme colors, plugin selection
- `quartz.layout.ts` — page layout and component arrangement
- `quartz/styles/custom.scss` — custom CSS overrides (preferred way to style)
- `quartz/static/` — static assets (icon, OG image, Giscus themes)

### Do NOT Edit (upstream-managed files)

- `quartz/components/` — all component source files
- `quartz/plugins/` — all plugin source files
- `quartz/styles/base.scss`, `variables.scss`, `callouts.scss`, `syntax.scss`
- `quartz/components/styles/` — component-specific SCSS
- `quartz/cli/`, `quartz/processors/`, `quartz/util/`, `quartz/i18n/`
- `quartz/build.ts`, `quartz/worker.ts`, `quartz/cfg.ts`
- `package.json`, `package-lock.json`, `tsconfig.json`

## Styling Guidelines

- **Always use `quartz/styles/custom.scss`** for CSS overrides. Do not modify upstream SCSS files.
- The theme uses warm earth-tone colors defined in `quartz.config.ts` under `theme.colors`.
- Typography: `Noto Sans TC` (header + body), `IBM Plex Mono` (code).
- Syntax highlighting: Catppuccin (`catppuccin-latte` for light, `catppuccin-frappe` for dark).
- Giscus comment themes are in `quartz/static/giscus/` (dark.css, light.css).

## Build & Verify

```bash
# Install dependencies
npm install

# Type check + format check
npm run check

# Build the site
npx quartz build

# Local dev server with hot reload
npx quartz build --serve

# Run tests
npm test
```

Output goes to `public/` (gitignored).

## Key Architecture

```
quartz.config.ts          — plugin selection, theme, site metadata
quartz.layout.ts          — page layout (left/right/beforeBody/afterBody)
quartz/styles/custom.scss — custom CSS (override point)
content/                  — blog content (git submodule, do not edit here)
```

Build pipeline: `Markdown → remark (parse) → transformer plugins → rehype (HTML AST) → filter plugins → emitter plugins → static HTML/RSS/sitemap`
