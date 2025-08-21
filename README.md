# Philoshi Hacker — GitHub Pages + Obsidian Notes

Minimal, fast, terminal-inspired personal site with Obsidian-powered notes via Jekyll collections.

## Features
- Hacker-green theme with monospace typography
- Responsive layout + mobile menu
- Notes collection (`_notes/`) published at `/notes/`
- Clean note layout with code/blockquote/table styling
- 404 page and accessible focus styles
- Rouge syntax highlighting + JS Run/Copy for `js` code blocks
- Tags page with client-side filter (`/tags/`)
- Wiki-links `[[Nama Catatan]]` parsing (client-side) dan Backlinks otomatis

## Structure
- `index.html` — Home page (uses `_layouts/base.html`)
- `_layouts/` — Shared `base` and `note` layouts
- `_notes/` — Markdown notes rendered to `/notes/:name/`
- `notes/index.html` — Notes index page
- `tags/index.html` — Tags index + filter
- `assets/styles.css` — Site styles
- `_config.yml` — Jekyll configuration

## Use with Obsidian
1. Keep public notes inside `_notes/` in this repo.
2. Optional front matter per note:
   ---
   title: My Note
   date: 2025-08-21
   tags: [tag1, tag2]
   ---
3. Commit and push — GitHub Pages renders notes at `/notes/`.

Tip: Use the Obsidian Git plugin to sync changes automatically.

### Wiki-links `[[...]]`
- Tulis tautan seperti `[[sejarah-hacker]]` atau `[[Sejarah Hacker — Dari MIT ke Open Source]]`.
- Pada saat muat halaman, skrip akan mengubah pola tersebut menjadi tautan ke catatan yang sesuai (berdasarkan slug atau judul).
- Halaman catatan juga menampilkan “Backlinks” (catatan lain yang menyebutkan Anda) otomatis saat build.

### Tags
- Tambahkan `tags: [a, b]` di front matter.
- Lihat semua tag dan filter catatan: `/tags/`.

## Local Preview
You can view the static files directly, or run a simple server:

```sh
python3 -m http.server
# open http://localhost:8000
```

To run Jekyll locally (optional), install Ruby/Jekyll and run `bundle exec jekyll serve`. GitHub Pages will build the site for you on push, even if you don’t run Jekyll locally.

## Deploy
This repository is a user site (`localan.github.io`). Push to `main` and GitHub Actions builds with Jekyll and deploys to Pages.

### GitHub Actions
- Workflow: `.github/workflows/static.yml`
- Steps: checkout → configure Pages → build with Jekyll → upload artifact → deploy
- Output URL: printed in the workflow summary (environment `github-pages`)

## Customize
- Colors/spacing: edit `assets/styles.css`
- Navigation: `_layouts/base.html`
- Home content: `index.html`
- Notes listing template: `notes/index.html`

## License
Public content is yours; code for this scaffold is provided as-is.
