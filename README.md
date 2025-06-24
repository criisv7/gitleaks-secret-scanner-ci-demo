# Gitleaks Secret Scanner - CI Demo

This repository is a live demonstration for testing the `gitleaks-secret-scanner` NPM package in a real GitHub Actions workflow.

## How It Works

1.  The repository contains a workflow file at `.github/workflows/secret-detection.yml`.
2.  This workflow is triggered on every **pull request** to the `main` branch.
3.  It uses `gitleaks-secret-scanner --diff-mode ci` to scan only the changes introduced in the pull request.
4.  If secrets are found, the job will fail, but it will still upload an HTML report as a workflow artifact named `gitleaks-scan-report`.

## How to Test

1.  Create a new branch from `main`.
2.  Add a file containing one or more secrets (e.g., a fake AWS key or a `DEMO_API_KEY_...`).
3.  Commit the changes and push the branch.
4.  Open a pull request to merge your branch into `main`.
5.  Go to the "Actions" tab or the pull request checks to see the workflow run.