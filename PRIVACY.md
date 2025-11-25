# Privacy

Veil SBG runs as a GitHub Action using the repository `GITHUB_TOKEN`. It:
- Reads repository metadata and security settings via the GitHub API.
- Does not send data to external services.
- Does not store secrets or personal data.

Logs are stored by GitHub under the repository’s default retention settings.
