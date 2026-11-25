# Home Repo

Personal starting point for working across Ash's repositories. Shared docs
live in `docs/`; add future shared skills under `.devin/skills/`. Read the
target repository's `AGENTS.md` before making changes and follow its local
rules. Create new ADRs in the target repository using
`docs/adr/0000-template.md` from this Home Repo.

## Other Repos

- github-infra (Terraform for GitHub repositories and Netlify settings):
  /home/ash/projects/github-infra. Clone from
  git@github.com:ash-c/github-infra.git if missing. Read its AGENTS.md first;
  infrastructure changes go through PRs, never local terraform apply.
- portfolio (React and TypeScript personal portfolio deployed to Netlify):
  /home/ash/projects/portfolio. Clone from
  git@github.com:ash-c/portfolio.git if missing. Read its AGENTS.md first and
  relevant docs/adr/ records before changing tooling or structure.
