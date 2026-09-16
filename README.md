# Dodgers News

GitHub-online-only RSS monitor for Dodgers coverage.

Tracks 40 names supplied in `config.json`.

Features:
- multilingual discovery (GDELT + Google News editions)
- Dodgers/MLB context filtering to reduce false positives
- automatic Spanish translation before RSS generation
- source included in every RSS title, e.g. `[ESPN] Shohei Ohtani...`
- smart duplicate detection across different publishers/languages
- only the most complete version of repeated news is kept
- alternate repeated sources are preserved in `alternate_sources`
- one master RSS plus individual RSS feeds per person
- automatic GitHub Actions run every hour at minute `:29`

GitHub workflow:
`.github/workflows/update.yml`

Run manually:
**Actions → Update Dodgers News RSS → Run workflow**

Generated:
- `docs/feed.xml`
- `docs/people/*.xml`
- `docs/index.html`
- `data/articles.json`

For public GitHub Pages:
**Settings → Pages → Deploy from branch → main → /docs**
