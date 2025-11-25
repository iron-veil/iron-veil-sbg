![Veil — Security Baseline Gate](https://github.com/iron-veil/iron-veil-sbg/actions/workflows/sbg.yml/badge.svg)

# Veil — Security Baseline Gate (SBG)

Veil checks pull requests for baseline GitHub security posture.

## Checks (MVP)
- Fails if `SECURITY.md` is missing.
- Fails if `.github/dependabot.yml` is missing.
- Warns if Code Scanning (default setup) is not enabled.
- Warns to enable Secret Scanning and Push Protection.

## Usage
1. Copy `.github/workflows/sbg.yml` into your repository.
2. Ensure `SECURITY.md` exists.
3. Ensure `.github/dependabot.yml` exists (a minimal config is included).
4. Open a pull request to trigger the check.

## Notes
- Uses the repository `GITHUB_TOKEN` with read-only scopes.
- No secrets are stored. No outbound calls beyond GitHub’s API.
