# AIrescue.dev

Landing page for AIrescue.dev — a service that fixes AI/vibe-coded projects.

## Tech Stack

- **Framework**: Astro 5 (static output, no SSR)
- **Package manager**: pnpm
- **TypeScript**: strict mode (`astro/tsconfigs/strict`)
- **Styling**: Astro scoped `<style>` per component + `src/styles/global.css` for shared styles
- **Fonts**: Plus Jakarta Sans + DM Mono via Google Fonts `<link>` tags
- **No client-side JS** — fully static site, no UI framework (React/Vue/etc.)

## Commands

- `pnpm dev` — start dev server
- `pnpm build` — build to `dist/`
- `pnpm preview` — preview production build

## Project Structure

```
src/
├── layouts/
│   └── Layout.astro          # HTML shell, <head>, font imports, global CSS import
├── styles/
│   └── global.css            # CSS variables, reset, .container, .btn, .section-header, responsive
├── components/
│   ├── Nav.astro             # Fixed top navbar
│   ├── Hero.astro            # Hero section with headline + CTAs
│   ├── TrustBar.astro        # Stats bar (codebases rescued, turnaround, etc.)
│   ├── Problems.astro        # 6 problem cards grid (#services anchor)
│   ├── Transform.astro       # Before/after comparison panels
│   ├── Process.astro         # 4-step process timeline (#process anchor)
│   ├── Proof.astro           # 3 testimonial cards
│   ├── Pricing.astro         # 3 pricing tiers (#pricing anchor)
│   ├── Cta.astro             # Bottom call-to-action
│   └── Footer.astro          # Footer with links
└── pages/
    └── index.astro           # Composes Layout + all components in order
```

## Conventions

- **Global CSS** is imported in Layout.astro frontmatter (`import '../styles/global.css'`), NOT in a scoped `<style>` block. This ensures shared classes (`.container`, `.btn`, `.section-header`) work inside child components.
- **Component CSS** goes in scoped `<style>` blocks within each `.astro` file.
- **CSS variables** are defined in `:root` in `global.css` — use them everywhere (e.g., `var(--accent)`, `var(--surface)`, `var(--border)`).
- **No JS** — don't add `client:*` directives or `<script>` tags unless explicitly needed.
- Components are PascalCase files, each containing their own markup + scoped styles.
- Anchor IDs for nav links: `#services` (on Problems), `#process` (on Process), `#pricing` (on Pricing).
