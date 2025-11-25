![Veil — Security Baseline Gate](https://github.com/iron-veil/iron-veil-sbg/actions/workflows/sbg.yml/badge.svg)

## Quick start (reusable)
Create `.github/workflows/veil.yml` in your target repo:

name: Security Baseline Gate
on: { pull_request: {}, push: { branches: ["**"] } }
jobs:
  veil:
    uses: iron-veil/iron-veil-sbg/.github/workflows/reusable-sbg.yml@v0.0.1

# Veil — Security Baseline Gate (SBG)

Security Baseline Gate — checks for SECURITY.md, Dependabot, Code Scanning default setup visibility, Secret Scanning/Push Protection, Dependency Graph, and SBOM presence.

## Checks (MVP)
- ❌ Fails if `SECURITY.md` is missing.
- ❌ Fails if `.github/dependabot.yml` is missing.
- ⚠️ Warns if Code Scanning (default setup) isn’t reachable via API.
- ⚠️ Warns to enable Secret Scanning + Push Protection.
- ✅/⚠️ Dependency Graph enabled.
- ✅/⚠️ SBOM file detected (CycloneDX/SPDX) or hint to publish via Dependency Submission.
  
## Usage
1. Copy `.github/workflows/sbg.yml` into your repository.
2. Ensure `SECURITY.md` exists.
3. Ensure `.github/dependabot.yml` exists (a minimal config is included).
4. Open a pull request to trigger the check.

## Notes
- Uses the repository `GITHUB_TOKEN` with read-only scopes.
- No secrets are stored. No outbound calls beyond GitHub’s API.

## Permissions & privacy
Uses the default `GITHUB_TOKEN` with `contents:read`, `security-events:read`, and `pull-requests:write` (for a sticky PR comment). No secrets are stored; no outbound calls beyond GitHub’s API.

- Docs: [Partner pitch](docs/PARTNER-PITCH.md) • [Security features](docs/SECURITY_FEATURES.md)
