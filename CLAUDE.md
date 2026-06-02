# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

@AGENTS.md

## Commands

```bash
npm run dev      # start dev server (http://localhost:3000)
npm run build    # production build
npm run lint     # run ESLint
```

There is no test suite yet.

## Stack

- **Next.js 16** with the App Router (`app/` directory)
- **React 19**
- **TypeScript**
- **Tailwind CSS v4** (configured via `@tailwindcss/postcss` in [postcss.config.mjs](postcss.config.mjs); no `tailwind.config.*` file — v4 uses CSS-first config in [app/globals.css](app/globals.css))

## Architecture

This is a freshly bootstrapped Next.js app. All routes live under `app/` using the App Router file-system conventions:

- [app/layout.tsx](app/layout.tsx) — root layout; applies Geist fonts as CSS variables and wraps all pages
- [app/page.tsx](app/page.tsx) — home route (`/`)
- [app/globals.css](app/globals.css) — global styles and Tailwind v4 directives

New routes go in `app/<route>/page.tsx`. Server Components are the default; add `"use client"` only when browser APIs or interactivity require it.
