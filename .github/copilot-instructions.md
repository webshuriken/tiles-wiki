# Copilot Instructions

## Project Overview

**Tiles Wiki** is a static wiki site built with [Astro](https://astro.build/). Content pages are authored in Markdown (`.md`) and MDX (`.mdx`).

## Build & Dev Commands

```bash
npm run dev        # Start local dev server (typically http://localhost:4321)
npm run build      # Production build (output to ./dist)
npm run preview    # Preview the production build locally
```

## Architecture

- `src/content/` — Wiki content collections (Markdown/MDX files). Each subfolder is a content collection defined in `src/content/config.ts`.
- `src/pages/` — Astro page routes. File-based routing: `src/pages/foo.astro` → `/foo`.
- `src/layouts/` — Shared page layouts (`.astro` components).
- `src/components/` — Reusable Astro/UI components.
- `public/` — Static assets served at the root (images, fonts, etc.).

## Key Conventions

- Content is managed through Astro's [Content Collections API](https://docs.astro.build/en/guides/content-collections/). Always define a schema in `src/content/config.ts` for each new collection.
- Prefer `.astro` components for layout and structure; use `.mdx` when a content page needs interactive or component-embedded elements.
- Frontmatter in content files must conform to the collection's Zod schema defined in `src/content/config.ts`.
- Static assets referenced in content should live in `public/` and be referenced with absolute paths (e.g., `/images/foo.png`).

## UI guidelines

- Application should have a modern and clean design.