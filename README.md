# Thesis dashboard

Live site: **https://liamkozma.github.io/thesis-dashboard/**

A single-file HTML record of the synthetic-data pipeline / r\* recovery-threshold
project: what was measured, on what data, with which model, and which conclusions
have survived.

## What is in here

| File | What it is |
| --- | --- |
| `index.html` | The whole dashboard. Self-contained: no external requests, all 24 figures embedded as data URIs. |
| `robots.txt` | Keeps the site out of search engines. |

The page is generated, not hand-edited. The source of truth and the build scripts
live on the cluster at `/work/ah2lab/LiamK/tidythesis/docs/notes/`:

- `PIPELINE_dashboard.v2.html` — the file published here
- `dashboard_build/` — `build.py` … `build5.py`, `concepts.py`, `assets.py`,
  `stampdata.py`, `verify.py`; re-run `./run.sh` to regenerate

## Updating the site

Copy the regenerated dashboard over `index.html`, keeping the noindex tag, then push:

```bash
cp /path/to/PIPELINE_dashboard.v2.html index.html
# re-add the noindex meta directly after <meta charset="utf-8">:
#   <meta name="robots" content="noindex, nofollow">
git add index.html
git commit -m "Update dashboard"
git push
```

GitHub Pages redeploys automatically, usually within a minute. The URL never changes.

## A note on visibility

This repository is **public**, because GitHub Pages requires that on a free account.
`robots.txt` and the `noindex` meta tag keep the site out of search results, but
anyone who has the URL can read it.
