# Veil — Security Baseline Gate (SBG)

## Purpose
- Enforce GitHub secure-by-default features at pull-request time.
- Reduce misconfiguration drift and make security posture visible to developers.

## Baseline checks (MVP)
- SECURITY.md present.
- Dependabot config present: `.github/dependabot.yml`.
- Code Scanning (default setup) visible via API; provide remediation link if not.
- (Warn) Secret Scanning and Push Protection should be enabled.

## Architecture
- GitHub Action using `actions/github-script`.
- Least-privilege permissions: `contents:read`, `security-events:read`, `pull-requests:write` (for PR comment).
- No secrets stored. No outbound network calls beyond the GitHub API.

## Roadmap
- Wrap as a GitHub App to use Checks API (richer status bubble, `checks:write`).
- Add dependency submission / SBOM detection.
- Optional artifact attestation verification on release workflows.

## Adoption
- Copy-paste workflow for any repo; works with the default `GITHUB_TOKEN`.
- Public README shows usage; PR checks + sticky comment provide remediation links.
