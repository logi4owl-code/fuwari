## Cursor Cloud specific instructions

### Project overview

Fuwari is a static blog template built with Astro, Svelte, and Tailwind CSS. It is a single-package project (not a monorepo) with no backend, no database, and no external service dependencies.

### Commands reference

See `README.md` "Commands" section for the full table. Key commands:

- **Dev server:** `pnpm dev` (port 4321)
- **Lint/format:** `pnpm lint` (Biome check + fix), `pnpm format` (Biome format)
- **Type checking:** `pnpm check` (Astro check), `pnpm type-check` (tsc --noEmit)
- **Build:** `pnpm build` (Astro build + Pagefind indexing)

### Known issues

- `pnpm check` and `pnpm type-check` both have pre-existing type errors in the repository (e.g., TS2322 in `Navbar.astro`, TS7006/TS2558 in `content-utils.ts`). These are not regressions; they exist on the `main` branch.
- The `preinstall` script enforces pnpm-only installs via `npx only-allow pnpm`. Do not use npm/yarn.

### Dev server notes

- The Astro dev server supports hot module replacement (HMR). File edits to `.astro`, `.svelte`, `.ts`, `.css`, and content files are picked up automatically.
- No external services or environment variables are required to run the dev server.

### Testing

There are no automated tests in this project. Validation is done through `pnpm check`, `pnpm lint`, and manual browser testing.
