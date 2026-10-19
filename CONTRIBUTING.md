# Contributing to dotablaze-tech

## Commit Messages

This org uses [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>

[optional body]
```

| Type | When to use |
|------|-------------|
| `feat` | New feature |
| `fix` | Bug fix |
| `chore` | Maintenance, deps, tooling |
| `docs` | Documentation only |
| `refactor` | Code change with no feature or fix |
| `test` | Adding or updating tests |
| `ci` | CI/CD pipeline changes |
| `perf` | Performance improvement |

In `platform`, only `fix` and `feat` commits cut a release (and deploy meowbot),
so use them for anything that changes shipped behavior or runtime dependencies.

**Examples:**
```
feat(meowbot): add a new slash command
fix(deps): update module github.com/bwmarrin/discordgo
chore(ci): pin action versions
```

## Branch Naming

```
<type>/<ticket-key>-<short-description>
```

**Examples:**
```
feat/DOTA-123-user-profile-command
fix/DOTA-124-token-expiry-check
docs/DOTA-10-add-agents-md
```

Omit the key only for work with no ticket.

## Pull Requests

- Keep PRs focused: one concern per PR
- Link the relevant issue if one exists
- Ensure CI passes before requesting review
- Use the PR template, but keep only the sections that have content: about
  150 words, written for the reviewer. No file-by-file list or restated diff
- Merges are **rebase** merges, so every commit reaches `main` as written:
  tidy the branch into commits that each stand alone before asking for review
- Never push directly to `main`

## AI-Assisted Commits

A commit made with an AI coding agent names the exact agent and model that
ran, in two trailers: the model actually used, never a copied example.

```
Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Assisted-by: Claude Code:claude-opus-5-5
```

(Codex: `Co-Authored-By: Codex <codex@openai.com>` and
`Assisted-by: Codex:<model-id>`.) Attribution lives in commits only: no
"Generated with" footer, robot emoji or attribution line in PR titles, bodies
or comments.

## Checks

Each repo enforces its own linting and formatting in CI. Run them before
opening a PR; see the repo's `AGENTS.md` for the exact commands.

- **platform**: `npx nx format:check` and `npx nx affected -t lint test build`
- **deployments**: `helm lint charts/<chart>` and `helm template` per environment

## Reporting Issues

Use the issue templates and fill them out fully. For security issues, follow
[SECURITY.md](SECURITY.md) instead.
