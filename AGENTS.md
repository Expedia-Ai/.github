# AGENTS.md

Default guidance for AI coding agents (Claude Code, Codex, Cursor, GitHub Copilot, and similar) working in Expedia-Ai repositories. Individual repos may extend or override this file.

## Working agreement

- Read `README.md`, `CONTRIBUTING.md`, and any per-repo `AGENTS.md` before changing files.
- Prefer minimal, reversible changes. No drive-by refactors outside the task scope.
- Never commit secrets, credentials, or `.env` files.
- Run the repo's tests, lint, type-check, and build (those it has) before declaring a task complete.

## Conventions

- Conventional Commits for commit messages and PR titles (`feat:`, `fix:`, `docs:`, `style:`, `refactor:`, `perf:`, `test:`, `build:`, `ci:`, `revert:`; never `chore:`, which is reserved for automation), ending with the Linear issue key (e.g. `feat: add rate limiting (EAI-42)`). Append `!` for breaking changes. Commits and PRs written with an AI agent that a person supervises on their own machine carry no attribution trailer or line; an agent working unattended (on a schedule) or in a cloud session keeps its default attribution.
- Default branch: `beta`, the pull request target; `main` is production (this `.github` repository has only `main`). Branches are named after the Linear issue in kebab-case (e.g. `eai-42-add-rate-limiting`). One PR per Linear issue into `beta`; the owners squash-merge.
- Agents never commit on, push to, or merge into `beta` or `main`, never force-push, and never use `--no-verify`.
- `CHANGELOG.md` is generated from the release notes. Never write or edit it.
- Match surrounding code style. Do not reformat unrelated lines.

## AI-authored code

- The PR description is a few plain, non-technical sentences on what the PR does, then Choices and Deviations only when there are real ones (the pull request template): no screenshots, checklists, test reports or anything unrelated to the PR's change.
- Ask before building when a change would depart from the Linear issue, an owner answer or the reference repo; the answer is the instruction. A departure that remains is listed under Deviations in the PR description, with its question for the owners, and is never kept in a log file. A check that wasn't run, an implementation choice (listed under Choices) or work the issue still has is not a deviation. Agent proposals are never recorded as owner approvals.
- Treat AI output as a draft: verify behavior, edge cases, and security implications before requesting review.
- Do not paste secrets, customer data, or proprietary IP into third-party AI services.
- Cite sources when an AI tool surfaces them; flag uncertain attribution rather than hide it.

## Quality gates

A change is ready to merge when:

- The PR title follows Conventional Commits.
- All required CI checks pass.
- Tests cover the new or changed behavior, in repos that have a test suite.
- Documentation is updated where the change is user-visible.
- The author self-reviewed it against the Linear issue and the reference repo and ran one `/code-review` pass, fixing real findings.
- A human reviewer has approved.

## Out of scope without explicit approval

- Rewriting public Git history.
- Major version bumps of runtime, framework, or database.
- Editing `.github/workflows/*` or branch protection rules.
- Releases, package publishes, or infrastructure changes.
- Packages, tools, services, or patterns that the Linear issue and the reference repos do not use.
