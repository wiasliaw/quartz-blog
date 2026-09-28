# quartz-blog

Personal blog at https://wiasliaw.io, built with Quartz v5 and deployed by Cloudflare Pages from the `release` branch.
Posts live in the `content/` git submodule (`wiasliaw/blog-content`); do not edit posts in this repo.
Publishing new posts = commit an updated `content` submodule pointer to `release` and push.

## Updating Quartz v5

- `v5` mirrors `upstream/v5` (https://github.com/jackyzha0/quartz). Never commit to it directly.
- `release` = `v5` + site customizations. Pushing `release` deploys to production.
- `v4-deprecated` is the archived v4 site. Read-only.

Sync flow:

```bash
git fetch upstream
git checkout v5 && git merge --ff-only upstream/v5 && git push origin v5
git checkout release && git merge v5
npm ci && npx quartz build   # verify before pushing release
```

## Editable files

Only these files are site-specific; everything else is upstream-owned and must stay untouched to keep merges clean:

- `quartz.config.yaml` — site config, theme, plugins, layout
- `quartz/styles/custom.scss` — CSS overrides
- `quartz/static/` — icon, OG image, giscus themes
- `.gitmodules`, `content` — submodule pointer
