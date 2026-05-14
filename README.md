# Dinaya Uptime Monitor

Powered by [Upptime](https://upptime.js.org). Monitors run on GitHub Actions every 5 minutes and write results to the `master`/`main` branch as commits.

This repo owns the **data**. The public-facing UI lives in [`dinaya-status`](../dinaya-status) and reads from the raw JSON in this repo.

## Setup

1. Create a new public GitHub repo named `dinaya-uptime-monitor` and push this folder to it.
2. Create a GitHub Personal Access Token (classic) with `repo` + `workflow` scopes.
3. Add it as a repo secret named `GH_PAT`.
4. Update `sites:` in `.upptimerc.yml` with the real production URLs.
5. Run the **Setup CI** workflow once manually from the Actions tab to initialize.

The monitors then run automatically on a cron.

## Data location

After the first run, status data lives at:

- `history/*.yml` — per-monitor history
- `graphs/*.png` — response time graphs
- `api/*.json` — machine-readable summaries (this is what `dinaya-status` consumes)
