# FF14 Raid Blog

A dark-themed solo blog for FFXIV raiding, built with [Astro](https://astro.build).
Posts are plain Markdown files — no database, no CMS, just files in GitHub.

## Quick start (local)

```bash
npm install
npm run dev
```

Then open http://localhost:4321 in your browser.

## Writing a post

1. Create a new file in `src/content/blog/`, e.g. `my-new-post.md`
2. Start it with frontmatter:

```md
---
title: "My post title"
date: 2026-10-26
tags: ["prog", "savage"]
---

Your content here...
```

- **Tags are free-form** — invent whatever you like. Tag pages and the tag index are generated automatically.
- **Draft mode:** add `draft: true` to the frontmatter to hide a post from the site while you work on it.
- **Images:** put files in `public/images/` and reference them like `![desc](/images/pic.jpg)`.
- **Filenames become URLs:** `my-new-post.md` → `/blog/my-new-post/`. Keep them lowercase with hyphens.

## Deploying with GitHub Pages

1. Create a repo on GitHub and push this project to it.
2. In the repo: **Settings → Pages → Source → GitHub Actions**.
3. Every push to `main` automatically rebuilds and deploys the site.
4. Once you know your live URL (e.g. `https://yourname.github.io/repo-name/`),
   set it as `site` in `astro.config.mjs` so RSS links are correct.

## Personalizing

- Site name, description, your name: edit `src/consts.ts`
- About page: edit `src/pages/about.astro`
- Colors/theme: edit `src/styles/global.css` (the accent color is `--accent`)

## Structure

```text
src/
  content/blog/     ← your posts (Markdown)
  content.config.ts ← post schema (title, date, tags, draft)
  layouts/          ← page shell
  components/       ← post cards, tag pills
  pages/            ← home, blog, tags, about, RSS
  styles/           ← dark theme
public/             ← images and static files
```
