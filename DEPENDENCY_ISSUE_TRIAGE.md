# Dependency Issue Triage

Source: GitHub Dependabot and security advisory emails received in Gmail between 2026-05-28 and 2026-06-10.

## Reported Issues

| Severity | Dependency or PR | Advisory / PR | Affected file |
| --- | --- | --- | --- |
| Critical | `shell-quote` | CVE-2026-9277 / GHSA-w7jw-789q-3m8p | `client/package-lock.json` |
| High | `tmp` | CVE-2026-44705 / GHSA-ph9p-34f9-6g65 | `client/package-lock.json` |
| Low | grouped npm/yarn updates | Dependabot PR #13 | `client/package.json`, `client/package-lock.json` |
| Low | `bn.js` | Dependabot PR #14 | `client/package-lock.json` |
| Low | `cipher-base` | Dependabot PR #15 | `client/package-lock.json` |
| Low | `handlebars` | Dependabot PR #16 | `client/package-lock.json` |
| Low | `lodash.template` | Dependabot PR #17 | `client/package-lock.json` |
| Low | `sha.js` | Dependabot PR #18 | `client/package-lock.json` |
| Low | `pbkdf2` | Dependabot PR #19 | `client/package-lock.json` |

## What Needs To Be Done

- Review the open Dependabot PRs and confirm whether the grouped PR supersedes individual PRs.
- Prioritize the critical `shell-quote` and high-severity `tmp` alerts.
- Install dependencies from `client/`, run the existing checks, and verify the app still builds.
- Merge the Dependabot PRs or recreate them if conflicts appear.

## Suggestions

- Handle the grouped npm/yarn PR first if it resolves multiple alerts cleanly.
- Use `npm audit` from `client/` after applying Dependabot updates to confirm remaining advisories.
- Avoid manually editing the lockfile unless the package manager produces the change.
