# pawanpatil.com

Minimalistic, coding-themed personal portfolio built with [Astro](https://astro.build).

## Commands

```bash
npm install      # Install dependencies
npm run dev      # Start dev server at localhost:4321
npm run build    # Build for production
npm run preview  # Preview production build locally
```

## Structure

```
src/
├── components/     # Reusable Astro components
├── content/
│   ├── blog/       # Markdown blog posts
│   └── projects/   # Markdown project write-ups
├── layouts/        # Page layouts (Base, BlogPost, ProjectPost)
├── pages/          # File-based routing
│   ├── blog/
│   ├── projects/
│   ├── experience.astro
│   └── index.astro
├── styles/         # Global CSS (light/dark theme)
├── consts.ts       # Site metadata
└── content.config.ts
```

## Deployment

Static output — deploy anywhere (Vercel, Netlify, Cloudflare Pages).

Set `site` in `astro.config.mjs` to `https://pawanpatil.com`.

## Publish a blog post

Create a Markdown file in `src/content/blog/`:

```md
---
title: 'Your title'
description: 'One clear sentence about the story.'
pubDate: 'Aug 10 2026'
tags: ['backend', 'lessons']
draft: true
---

Start writing here.
```

Drafts stay out of the blog, RSS feed, and production build. Change `draft` to
`false` (or remove the line) when the post is ready to publish.
