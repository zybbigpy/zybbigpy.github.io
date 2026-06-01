# CLAUDE.md — Project Instructions

## Publication data — critical rule

`content/CV/papers.bib` is the **authoritative source of truth** for all publications. It was curated by the repository owner. When generating or updating `content/Research/index.typ` or any other page that lists publications:

- **Never add, remove, or modify a paper entry based on web search results, agent findings, or any external source that has not been verified by the owner.**
- The bib file takes precedence over anything returned by arXiv searches, Semantic Scholar, Google Scholar, or any other tool.
- If you believe a preprint has been published in a journal, **do not update the citation** unless the owner explicitly confirms the journal reference (title, volume, page, DOI).
- Do not invent or guess DOIs, journal names, volume numbers, or author lists.

### Correct workflow for updating publications

1. Read `content/CV/papers.bib` — use it as the sole source for all paper metadata.
2. Render each entry in `content/Research/index.typ` exactly as specified in the bib file.
3. If a web search suggests a paper has been published, report the finding to the owner and wait for confirmation before changing anything.

## Site structure

- `config.typ` — shared template (at repo root)
- `content/index.typ` — homepage; imports from `../config.typ`
- `content/*/index.typ` — subpages; must import with `#import "../index.typ": template, tufted`
- Build: `typst compile --root .. --font-path assets --features html --format html <input> <output>`
- Deploy: GitHub Actions on push to `main` (`.github/workflows/deploy.yml`)
