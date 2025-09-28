# Repository Guidelines

## Project Structure & Module Organization
- `src/`: React + TypeScript app. Key folders: `components/`, `hooks/`, `tabs/`, `services/` (save decryptor), `translations/` (XML + `custom_translations.json`). Assets in `src/assets/`.
- `public/`: Static files served as-is.
- Tooling: `index.html`, `vite.config.ts`, `eslint.config.js`, `tsconfig*.json`.
- `build/`: Packaged artifacts (e.g., `SavegameAnalyzer.exe`). Do not edit.
- Scripts: `*.cjs` for translations, packaging, and serving.

## Build, Test, and Development Commands
- `npm install` — Install dependencies.
- `npm run dev` — Start Vite dev server with HMR.
- `npm run build` — Type-check and bundle to `dist/`.
- `npm run preview` — Serve `dist/` locally.
- `npm run lint` — Run ESLint checks.
- `npm run serve:dist` — Lightweight static server for `dist/`.
- `npm run package:win` — Create `build/SavegameAnalyzer.exe` (bundled server + assets).
- `npm run deploy` — Publish `dist/` to GitHub Pages.

## Coding Style & Naming Conventions
- Stack: TypeScript 5, React 19, Vite 7, Tailwind 4.
- Indent 2 spaces; use semicolons and double quotes.
- Components in PascalCase `.tsx`; hooks start with `use*`.
- Prefer functional components and hooks.
- Styling via Tailwind utility classes (`src/index.css`).
- Run `npm run lint` before committing.

## i18n & Content
- Route all UI text through `useTranslation()`.
- Add keys in English and update `src/translations/custom_translations.json`.
- Use helper scripts (e.g., `updateTranslations.cjs`) to sync/generate templates.

## Testing Guidelines
- No formal test suite yet; verify with `npm run dev` and `npm run build`.
- If adding tests, colocate as `*.test.ts`/`*.test.tsx`, keep fast and focused.

## Commit & Pull Request Guidelines
- Messages: short, present-tense (e.g., "Update: improve journal UI", "Fix: decryptor edge case"). Conventional Commits optional.
- PRs: describe motivation, list changes, link issues, and include screenshots for UI changes.
- Ensure `npm run lint` and `npm run build` pass; avoid committing `build/` or `dist/`.

## Security & Behavior
- App runs fully locally; do not add telemetry or external network calls.
- Do not change the AES key in `src/services/decryptor.ts` without strong justification and testing.

