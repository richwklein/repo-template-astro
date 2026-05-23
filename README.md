# repo-template-astro

Astro + TypeScript + Tailwind CSS template for [@richwklein](https://github.com/richwklein) projects, generated from [repo-template-base](https://github.com/richwklein/repo-template-base).

Adds on top of the base:

- **Astro 6** with TypeScript strict mode and path aliases
- **Tailwind CSS 4** via `@tailwindcss/vite`
- **ESLint 10** + **Prettier 3** + Astro/Vitest plugins
- **Vitest 4** with v8 coverage reporting
- **npm** as the package manager (Node 22.21.0 pinned in `.tool-versions`)
- **Workflows**: `code-lint`, `code-test`, `code-build`, `report-coverage`, `release-please`
- **Composite action**: `setup-tools` that installs Node + runs `npm ci`
- **release-please** for semantic-release of `package.json` from Conventional Commits

## Use this template

Click **Use this template → Create a new repository** on GitHub, then run through the checklist below.

### Post-template checklist

- [ ] `npm install` to populate `node_modules` (lockfile is committed; this just hydrates).
- [ ] Update `package.json` `name`, `description`, and `version`.
- [ ] Update `release-please-config.json` `package-name` to match `package.json` `name`.
- [ ] Replace `src/pages/index.astro` and `src/layouts/Base.astro` with your real homepage and layout.
- [ ] Update `astro.config.ts` with the integrations you need (sitemap, mdx, adapter, etc.).
- [ ] Update `.vscode/settings.json` `cSpell.words` for project-specific terms.
- [ ] Update `README.md` with your project description (replace this content).
- [ ] **Apply repo settings and branch protection** — run `/repo-template-audit richwklein/repo-template-astro` from a Claude Code session; the audit skill compares this repo's live GitHub settings and reports any drift. Required status check contexts for this template are `lint`, `test`, `build`, `analyze (actions)`, and `analyze (javascript-typescript)`. Add the branch ruleset **after** the first PR has run so the status check names are registered.

## Scripts

```bash
npm run dev            # start dev server
npm run build          # type-check (astro check) + production build
npm run preview        # preview the production build
npm run lint           # eslint
npm run lint:fix       # eslint --fix
npm run format         # prettier --check
npm run format:fix     # prettier --write
npm run test           # vitest run
npm run test:coverage  # vitest run --coverage
npm run verify         # lint + format + test + build (use before pushing)
npm run clean          # remove .astro, dist, node_modules, coverage
```

## Releases

Releases are automated via [release-please](https://github.com/googleapis/release-please-action). Use [Conventional Commits](https://www.conventionalcommits.org/) on `main`; release-please opens a release PR that bumps `package.json` and updates `CHANGELOG.md`. Merge the release PR to cut a GitHub Release + git tag.

## Audit drift

Run `/repo-template-audit` from a Claude Code session in the repo directory to check whether tracked files and GitHub repo settings still match the canonical sources in `repo-template-base` and `repo-template-astro`.

## License

[MIT](LICENSE) © Richard Klein
