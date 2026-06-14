# AGENTS.md — LUX client web build

Shared instructions for any AI agent (Cursor, Claude Code, Codex) working in this
repo. Keep this file lean and point to other files rather than pasting their
contents, so it doesn't go stale.

## What this repo is

A `[CLIENT NAME]` marketing website built by LUX. The goal is a fast,
search-visible, conversion-oriented site we can hand off cleanly. Optimize for
clarity, performance, and SEO/AEO — not cleverness.

## Commands

> Adjust to the actual stack and delete what doesn't apply.

- `npm run dev` — local dev server
- `npm run build` — production build
- `npm run typecheck` — run before finishing any series of edits
- `npm run lint` — lint + format

## Stack & conventions

- Tailwind for styling — see `.cursor/rules/tailwind.mdc`.
- Semantic HTML first: real `<header> <nav> <main> <section> <article> <footer>`.
  Headings in order, exactly one `<h1>` per page.
- TypeScript for any JS. No `any` as an escape hatch.
- Prefer functional, composable components. Use `components/[Canonical].tsx` as
  the reference pattern for new components.
- Accessibility is non-negotiable: alt text on every image, labelled form
  controls, visible focus states, AA contrast minimum.

## Architecture

- Pages/routes mirror the site map. One section component per page region.
- Keep editable content (copy, FAQs, schema data) separate from layout where the
  stack allows, so non-devs can edit copy without touching markup.
- For self-contained HTML deploys (Cloudflare Pages), inline everything into one
  file **only** when explicitly building that target.

## Working style

- Be concise. Don't explain standard patterns unless asked.
- If a change is effectively identical to existing code, say "no changes needed."
- Never commit without review. Never delete files or run destructive git
  commands without explicit approval.
- Before importing a package, verify it's installed (`npm list <pkg>`) — don't
  assume it exists from training data.

## SEO/AEO baseline

Search and answer-engine visibility is core to every LUX build. The full
checklist lives in `.cursor/rules/marketing-site.mdc`.
