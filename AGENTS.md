# Home Repo

Personal starting point for working across Ash's repositories. Shared docs
live in `docs/`; add future shared skills under `.devin/skills/`. Read the
target repository's `AGENTS.md` before making changes and follow its local
rules. Create new ADRs in the target repository using
`docs/adr/0000-template.md` from this Home Repo.

## Shared scripts

- `scripts/npm-deps.mjs`: dependency maintenance for any npm repository with a
  `package-lock.json` (Node 24, no dependencies). Run it from the target
  repository's root, e.g. `node ../home-repo/scripts/npm-deps.mjs report`.
  `report` lists `npm audit` advisories, patch and minor updates within each
  direct dependency's current major, and available majors, without changing
  anything. `security` runs `npm audit fix` (never `--force`) and bumps exact
  direct pins to a non-major fixed version. `update [--exclude a,b]` bumps
  direct dependencies within their current major, keeping the `^`/`~`/exact
  prefix. `0.x` minors count as majors. Add `--nested` to `security` or
  `update` when the hoisted install churns unrelated transitive lockfile
  entries, and `--json` for raw data. Each command prints Markdown tables for
  PR descriptions. It never takes a major; run the target repository's checks
  afterwards.

## Other Repos

- github-infra (Terraform for GitHub repositories and Netlify settings):
  /home/ash/projects/github-infra. Clone from
  git@github.com:ash-c/github-infra.git if missing. Read its AGENTS.md first;
  infrastructure changes go through PRs, never local terraform apply.
- portfolio (React and TypeScript personal portfolio deployed to Netlify):
  /home/ash/projects/portfolio. Clone from
  git@github.com:ash-c/portfolio.git if missing. Read its AGENTS.md first and
  relevant docs/adr/ records before changing tooling or structure.
