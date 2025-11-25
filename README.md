![Veil - Security Baseline Gate](https://github.com/iron-veil/iron-veil-sbg/actions/workflows/sbg.yml/badge.svg)

# Veil - Security Baseline Gate (SBG)

Security baseline checks for GitHub repositories. Veil verifies essential hardening features at pull-request time and posts clear, auditable results.

---

## What Veil checks

- Fail if `SECURITY.md` is missing.
- Fail if `.github/dependabot.yml` is missing.
- Warn if Code Scanning (CodeQL) default setup is not reachable via API.
- Warn if Secret Scanning and Push Protection are not enabled.
- Pass/Warn based on Dependency Graph being enabled in repo settings.
- Pass/Warn based on SBOM presence (CycloneDX or SPDX file in the repo, or guidance to publish via Dependency Submission).

---

## Quick start (reusable workflow)

Use Veil in any repository via a reusable workflow.

Create `.github/workflows/veil.yml` in the target repo with:

    name: Security Baseline Gate
    on:
      pull_request:
      push:
        branches: ["**"]
    jobs:
      veil:
        uses: iron-veil/iron-veil-sbg/.github/workflows/reusable-sbg.yml@v0.0.1

If you have not published a release tag yet, use `@main` temporarily and switch to the latest tag later.

---

## Using inside this repository

Veil runs on both `push` and `pull_request` and can be triggered manually from the **Actions** tab. Results appear in:
- the run summary (Checks tab), and
- a sticky PR comment that updates on re-runs.

---

## Enable these GitHub features (recommended)

- Code Scanning (CodeQL): Security → Code scanning alerts → Default setup → Enable  
- Secret Scanning and Push Protection: Settings → Code security & analysis → Enable  
- Dependency Graph: Settings → Code security & analysis → Enable

---

## SBOM options

- Commit a CycloneDX or SPDX file to the repository (for example: `sbom.json`, `bom.xml`, `sbom.spdx.json`).  
- Or publish dependencies via the Dependency Submission API during builds.

---

## Permissions and privacy

Veil uses the repository `GITHUB_TOKEN` with:
- `contents: read`
- `security-events: read`
- `pull-requests: write` (for the sticky PR comment)

No secrets are stored. No outbound network calls beyond the GitHub API.

---

## Project docs

- Partner overview: `docs/PARTNER-PITCH.md`  
- Security features referenced: `docs/SECURITY_FEATURES.md`

---

## Support

See `SUPPORT.md`. Security issues should be reported via private Security Advisories (see `SECURITY.md`).

---

## License

[MIT](LICENSE)