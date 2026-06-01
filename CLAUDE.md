# CLAUDE.md — Project Instructions

## Publication data

**arXiv is the primary source of truth** for publication metadata (authors, journal-ref, DOI). The owner does not want to maintain `content/CV/papers.bib` manually.

### Workflow for generating/updating the Research page

1. Fetch papers from arXiv for author "Wangqian Miao": `https://arxiv.org/search/?searchtype=author&query=Miao+Wangqian`
2. For each paper, check the abstract page for a `Journal-ref` field. If present, use the journal citation and DOI; if absent, label it as a preprint.
3. **Identity check — critical:** `content/CV/papers.bib` lists known papers by this owner. Before including any arXiv result, verify it overlaps with the bib file (same title or arXiv ID). Do not include papers by other authors who happen to share the name "Wangqian Miao" or "Miao W".
4. New papers found on arXiv that are not yet in the bib file may be included if the title/topic is clearly consistent with this owner's research area (condensed matter theory: moiré, electron crystals, topology, 2D materials).
5. Never fabricate or guess a journal reference — only use what the arXiv `Journal-ref` field explicitly states.

### Research summary style

- 2–4 sentences, no collaborator names, no affiliation, no position titles.
- Infer themes from the most recent ~2 years of papers only.

## Site structure

- `config.typ` — shared template (at repo root)
- `content/index.typ` — homepage; imports from `../config.typ`
- `content/*/index.typ` — subpages; must import with `#import "../index.typ": template, tufted`
- Build: `typst compile --root .. --font-path assets --features html --format html <input> <output>`
- Deploy: GitHub Actions on push to `main` (`.github/workflows/deploy.yml`)
