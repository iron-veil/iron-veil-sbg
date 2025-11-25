# Veil reusable workflow — consumer setup

1. In the target repo, create `.github/workflows/veil.yml`:
   ```yaml
   name: Security Baseline Gate
   on:
     pull_request:
     push:
       branches: ["**"]
   jobs:
     veil:
       uses: iron-veil/iron-veil-sbg/.github/workflows/reusable-sbg.yml@v0.0.1
