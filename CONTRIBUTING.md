# Contributing to Veil SBG

All changes go through pull requests.

## Principles
- Deterministic workflows only; no external network calls beyond the GitHub API.
- Least privilege for every permission change.
- Clear upgrade path and rollback for releases.

## Development
- Default branch: `main`.
- YAML: 2-space indent. Markdown: keep lines readable.
- Add tests by opening a PR and verifying the Veil table.

## Pull Request requirements
- Explain the change and risk.
- Include a permissions diff for any workflow edit.
- Update README/docs if behavior changes.

## Release
- Update `CHANGELOG.md`.
- Tag `vX.Y.Z` and publish a GitHub Release.

## Security
- Report vulnerabilities via private Security Advisories (see `SECURITY.md`).
