# Repository Guidelines

## Project Structure & Module Organization
- `src/`: Application source. Entry at `src/index.ts`; main component in `src/App.ripple`.
- `src/assets/`: Static assets (e.g., `favicon.ico`).
- `index.html`: Vite HTML entry mounting `#root`.
- `vite.config.js`: Vite + `vite-plugin-ripple` config (dev server on port 3000).
- `tsconfig.json`: TypeScript settings for Ripple/Vite.
- `.prettierrc`: Formatting rules (Ripple plugin enabled).

## Build, Test, and Development Commands
- `pnpm install`: Install dependencies.
- `pnpm run dev` or `pnpm start`: Run Vite dev server at `http://localhost:3000`.
- `pnpm run build`: Production build to `dist/`.
- `pnpm run serve`: Preview the production build locally.
- `pnpm run format`: Format codebase with Prettier.
- `pnpm run format:check`: Verify formatting without changing files.
- Optional: If you use `mise`, tasks like `mise run build` map to the same PNPM scripts.

## Coding Style & Naming Conventions
- Indentation: tabs (see `.prettierrc`, `useTabs: true`).
- Quotes: single quotes; line width 100.
- Components: PascalCase for `.ripple` components (e.g., `App.ripple`).
- Variables/functions: camelCase; constants UPPER_SNAKE_CASE when appropriate.
- File layout: colocate component styles inside `.ripple` when simple; factor shared styles/utilities into `src/` modules as needed.

## Testing Guidelines
- Tests are not configured yet. Recommended: Vitest + jsdom.
- Suggested layout: `src/__tests__/*.test.ts` (match source module names).
- Suggested scripts: `"test": "vitest", "test:watch": "vitest --watch"`.
- Aim for meaningful unit tests around components and helpers; prefer fast tests.

## Commit & Pull Request Guidelines
- Commits: Prefer Conventional Commits (e.g., `feat: add counter`, `fix: handle null target`).
- Keep commits scoped and descriptive; reference issue IDs where applicable.
- Pull Requests: include a clear summary, screenshots/GIFs for UI changes, reproduction steps, and checklist of affected areas. Link related issues.

## Security & Configuration Tips
- Runtime: Node >= 20 (see `package.json`); repo also includes `mise.toml` with Node 22 and PNPM 10.
- Never commit secrets. Use Vite env files (e.g., `.env.local`) for local-only values and ensure they’re git-ignored.
- Audit dependencies periodically and keep `vite`, `ripple`, and plugins up to date.
