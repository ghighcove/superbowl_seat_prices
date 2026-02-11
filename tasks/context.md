# Super Bowl Ticket Price Analysis - Session Context

## Last Updated: 2026-02-09

## Current State
- **Project is PUBLISHED.** Article live on Medium, repo public on GitHub with Pages enabled.
- Two deliverables complete: Jupyter notebook with 6 interactive Plotly charts + Medium article (~1,600 words)
- 6 PNG chart exports in `exports/` (91-168 KB each, 2x scale for retina)
- 60-row ticket price dataset compiled from 8+ free sources
- CPI data covering 1967-2026 (2026 is estimated at 330.0)
- GitHub repo: `ghighcove/superbowl_seat_prices` — **public**, GitHub Pages enabled

## Active Work
- Refactored the `/claude-md-audit` skill and audited the global CLAUDE.md

## Key Design Decisions
- **Two outputs**: Medium article (static PNGs) + Jupyter notebook (interactive Plotly, shareable on GitHub/nbviewer)
- **Histograms**: Simulated log-normal distributions using midpoint of low/high as log_mean anchor, soft filtering instead of hard clipping (avoids artificial spikes at boundaries)
- **Data sources**: Casino.org, TickPick, Yahoo Sports, Marco News/USA TODAY, Barry's Tickets, CBS News, GOBankingRates, InvestorPlace for tickets; BLS CPI-U for inflation
- **Inflation method**: `adjusted = nominal * (cpi_2025 / cpi_year)` using CPI-U annual averages, target year 2025 (CPI=321.9)
- **Visualization library**: Plotly 6.5.2 with `plotly_white` template, colorblind-safe palette, 2x scale PNG exports via kaleido
- **Annotation rendering**: Avoid `$` characters and `<br>` tags in Plotly annotations for static PNG export — they render as garbled text. Use plain text and commas instead.
- **Attribution convention**: Global CLAUDE.md mandates an attribution preface in all research article drafts, with dynamic model name insertion
- **Medium import method**: GitHub Pages (not raw.githubusercontent.com) — raw URLs serve `text/plain` which Medium rejects. See `tasks/lessons.md` for full recipe.
- **claude-md-audit refactor**: Web searches are now opt-in (default: score using built-in rubric + Claude knowledge). User is prompted to choose project-level vs global CLAUDE.md before auditing. Bumped to v0.2.0.
- **Global CLAUDE.md optimization**: Cut "Adaptive Thinking" section (redundant), cut "just fix bugs" line (redundant), merged critical-decisions into Planning & Verification, compressed Article Attribution to inline template. 69 -> 59 lines, score 86/100 Grade B.

## Recent Changes (this session)
- `C:\Users\ghigh\.claude\skills\claude-md-audit\SKILL.md` — Restructured phases: Phase 1 asks target (project/global), Phase 2 evaluates without web searches by default, web search offered as opt-in after scoring. Bumped to v0.2.0.
- `C:\Users\ghigh\.claude\skills\claude-md-audit\README.md` — Updated description, "What It Does" bullets, and usage examples to reflect project/global support and opt-in web search.
- `C:\Users\ghigh\.claude\CLAUDE.md` — Optimized from 69 to 59 lines. Removed redundancies, added escape valves, compressed attribution template.
- Pushed claude-md-audit changes to `ghighcove/claude-md-audit-skill` on GitHub (commit `9b14325`).

## Blockers / Open Questions
- No blockers.
- Consider whether Article Attribution section should migrate to project-level CLAUDE.md files (flagged in audit as borderline global)

## Next Steps
1. Test `/claude-md-audit` in a fresh session to verify full flow (target prompt -> scoring -> optional web search -> report)
2. Optional polish: separate Median/Mean annotations in pooled histogram (cosmetic)

## Environment
- Platform: Windows (win32), Python 3.8.0 (32-bit) at E:\Python\Python38-32
- Working directory: G:\ai\superbowl_seat_prices
- Skills directory: C:\Users\ghigh\.claude\skills\
- claude-md-audit repo: https://github.com/ghighcove/claude-md-audit-skill.git (master branch)
- Key packages: plotly 6.5.2, pandas 2.0.3, numpy 1.24.3, scipy 1.9.1, kaleido 1.2.0
- GitHub Pages URL: https://ghighcove.github.io/superbowl_seat_prices/
