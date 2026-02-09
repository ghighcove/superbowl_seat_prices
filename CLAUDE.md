# Super Bowl Ticket Price Analysis

## Project Overview
Jupyter Notebook + Medium article analyzing 60 years of Super Bowl ticket prices (1967-2026) with inflation adjustment, era analysis, and distribution modeling.

## Architecture
- `notebooks/` — Analysis notebook with 6 interactive Plotly charts
- `exports/` — PNG chart exports (2x scale for retina)
- `article/` — Medium draft (markdown) + Medium-ready HTML
- `data/` — Ticket price CSV and CPI data

## Key Conventions
- Inflation adjustment: `adjusted = nominal * (cpi_2025 / cpi_year)` using BLS CPI-U
- All monetary values stated in 2025 dollars unless noted
- Log-normal simulation for price distributions (midpoint anchor, soft filtering)
- Attribution preface required per global CLAUDE.md

## Article Optimization (GEO)
When writing or updating the Medium article (`article/medium_draft.md` + `article/medium_ready.html`):
- Run the `seo-for-llms` skill before publishing to audit LLM discoverability
- Both files must be edited in sync — markdown source and HTML are maintained independently
- Use descriptive H2 headings (topic + key finding), not clever/vague labels
- Include a "Key Findings" summary block near the top for RAG retrieval
- Lead sections with conclusions (BLUF), then support with narrative
- Define acronyms on first use (CPI-U, etc.)
- Link data sources inline, not just in a footer
- After edits, commit and push to update the GitHub Pages URL that Medium reads from

## Data Sources
Casino.org, TickPick, Yahoo Sports, Marco News/USA TODAY, Barry's Tickets, CBS News, GOBankingRates, InvestorPlace (tickets); BLS CPI-U (inflation).

## Running
1. `pip install -r requirements.txt`
2. Run the analysis notebook
3. Chart exports auto-generated to `exports/`
