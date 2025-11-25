# Veil — Security Baseline Gate (SBG)

Purpose
- Enforce GitHub secure-by-default features at pull request time.
- Reduce misconfiguration drift; make security posture visible to developers.

Baseline checks (MVP)
- SECURITY.md present.
- Dependabot config present (.github/dependabot.yml).
- Code Scanning (default setup) visible via API; provide remediation link if not.

Architecture
- GitHub Action using actions/github-script.
- Least-privilege permissions: contents:read, security-events:read; pull-requests:write for PR comment.
- No secrets stored. No outbound network calls beyond GitHub API.

Roadmap
- Add Checks UI via GitHub App (checks:write) for richer status.
- Add dependency submission/SBOM detection.
- Optional artifact attestation verification on release workflows.

Adoption
- Copy-paste workflow for any public repo; works with default GITHUB_TOKEN.
- Public documentation in README; sample screenshots in PR checks and comments.
