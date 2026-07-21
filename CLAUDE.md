# Sayword Dev Blog — Repo Guide

MkDocs Material site for developer notes, changelogs, and how-tos. Deployed to GitHub Pages
via GitHub Actions on every push to `main`.

- Live site: https://medassistant-net.github.io/sayword/
- Source: `docs/`
- Config: `mkdocs.yml`
- Deploy workflow: `.github/workflows/deploy.yml` (builds with `mkdocs gh-deploy --force`, pushes to `gh-pages`)

## Local preview

```bash
python3 -m venv .venv        # first time only
.venv/bin/pip install -r requirements.txt
.venv/bin/mkdocs serve       # live-reload at http://127.0.0.1:8000
```

## Adding an article

1. Pick the section: `docs/changelog/`, `docs/howtos/`, or `docs/notes/`.
2. Create a new Markdown file, e.g. `docs/howtos/2026-07-21-my-topic.md`.
3. Link it from that section's `index.md` (top-level `mkdocs.yml` `nav:` only lists the
   three section index pages, not individual articles — the index pages are the table of contents).
4. Commit and push to `main` — Actions builds and deploys automatically.

## Screenshots

- Place image files under `docs/assets/images/`.
- Reference with a relative Markdown link: `![alt text](../assets/images/foo.png)`.
- The `glightbox` plugin auto-wraps images in a click-to-zoom lightbox — no extra markup needed.

## Videos

Don't commit video files to this repo (bloats git history, slow clones, no LFS configured).
Instead:
- Embed a YouTube/Vimeo iframe, or
- Host the file externally (e.g. attach to a GitHub Release, or an object store) and embed with
  an HTML5 `<video>` tag pointing at that URL.

## Multi-language pages (i18n)

Uses `mkdocs-static-i18n` in `suffix` mode:
- Default language (English) uses the plain filename: `index.md`.
- Other languages add a locale suffix before `.md`: `index.ru.md`.
- Currently configured locales: `en` (default), `ru`. See `languages:` under the `i18n` plugin
  in `mkdocs.yml` to add more.
- A language switcher appears automatically in the header — no per-page config needed beyond
  creating the suffixed file.

## Release builds

Don't commit binaries/build artifacts to this repo. Use **GitHub Releases** on the relevant
product repo instead:

```bash
git tag v0.1.0 && git push --tags
gh release create v0.1.0 ./dist/*.zip
```

Then link to the release from a changelog entry:

```markdown
## v0.1.0 — 2026-07-21
[Download](https://github.com/<org>/<repo>/releases/tag/v0.1.0)
```

## Known cosmetic issue

`mkdocs build --strict` currently fails on a benign `mkdocs-rss-plugin` / `mkdocs-static-i18n`
config-validation interaction (`date_from_meta.default_time` re-parsed on the second per-locale
build pass). Non-blocking — `mkdocs gh-deploy` (used in CI) does not use `--strict`, so deploys
are unaffected. Safe to ignore unless it starts failing CI.
