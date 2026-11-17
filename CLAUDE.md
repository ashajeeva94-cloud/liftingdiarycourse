# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Next.js version warning

This project uses Next.js 16 / React 19, which has breaking changes versus older Next.js. Per `AGENTS.md`, read the relevant guide in `node_modules/next/dist/docs/` (sections: `01-app`, `02-pages`, `03-architecture`, `04-community`) before writing Next.js code, and heed deprecation notices.

## Commands

- `npm run dev` — start dev server (http://localhost:3000)
- `npm run build` — production build
- `npm run start` — serve the production build
- `npm run lint` — ESLint (flat config in `eslint.config.mjs`, extends `eslint-config-next` core-web-vitals + typescript)

No test framework is configured.

## Architecture

Freshly scaffolded `create-next-app` project (App Router, TypeScript, Tailwind CSS v4). All code lives under `src/app/` (`layout.tsx`, `page.tsx`, `globals.css`); the `@/*` import alias maps to `./src/*`.

Tailwind v4 is wired through Turbopack rather than PostCSS: `next.config.ts` registers `@tailwindcss/turbopack` as a loader for `*.css`. Keep that rule when editing the config.
