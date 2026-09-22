# Dodgers News

GitHub-online-only RSS monitor for Los Angeles Dodgers coverage.

## Tracked names

The project now tracks **56 names**.

The list includes current players, injured/minor-league players, staff/front-office names, franchise legends, and additional players appearing on the supplied Dodgers roster.

## Timeout-safe batching

The 56 tracked names are split evenly:

- **Batch 1:** 28 names
- **Batch 2:** 28 names

GitHub Actions runs every hour. After a successful run, the next execution uses the other batch.

Rotation state is stored in:

`data/state.json`

## Rolling two-hour window

Each run only considers stories published during the previous **2 hours**.

Google News publication dates are checked before redirect decoding and article extraction, so old search results are discarded before expensive processing.

## Features

- GDELT + Google News multilingual discovery
- Dodgers / Los Angeles / MLB context filtering
- automatic Spanish translation
- source displayed at the beginning of each RSS title
- smart duplicate detection
- keeps the most complete version of repeated coverage
- master RSS plus individual feeds in `docs/people/`
- newly accepted stories translated immediately
- only a limited number of older incomplete translations retried per run

## Workflow

`.github/workflows/update.yml`

Action name:

**Update Dodgers News RSS**

Runs every hour at minute `:29`.

## Generated files

- `docs/feed.xml`
- `docs/people/*.xml`
- `docs/index.html`
- `data/articles.json`
- `data/state.json`

Do not delete `data/state.json` unless you intentionally want to reset the batch rotation.
