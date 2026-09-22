# SolWear docs

Source for the SolWear developer documentation published at
**[docs.solwear.tech](https://docs.solwear.tech)**.

The content is Markdown under [`pages/`](pages/) (plus `ARCHITECTURE.md` and
`LEGACY_MIGRATION.md`), with the navigation and page order defined in
[`site.json`](site.json). A small zero-dependency generator renders it to static
HTML with the theme in [`theme/style.css`](theme/style.css).

## Build

```bash
npm run build     # render pages/ -> dist/
npm run serve     # build and serve locally
```

## Structure

| Path | What |
| --- | --- |
| `pages/*.md` | Documentation pages |
| `ARCHITECTURE.md`, `LEGACY_MIGRATION.md` | Long-form reference pages linked from the nav |
| `site.json` | Nav groups, page order, titles and output names |
| `theme/style.css` | Docs theme |
| `build.mjs`, `serve.mjs` | Static site generator and local server |

## Contributing

Add a page under `pages/`, then add it to the right group in `site.json`. Use
relative `*.md` links between pages; the build rewrites them to `.html`.

Licensed under Apache-2.0.
