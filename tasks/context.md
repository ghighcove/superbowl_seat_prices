# Super Bowl Ticket Price Analysis - Session Context

## Last Updated: 2026-02-08

## Current State
- **Project is COMPLETE.** All 6 tasks finished, all verification checks pass.
- Two deliverables ready: Jupyter notebook with 6 interactive Plotly charts + Medium article draft (~1,600 words)
- 6 PNG chart exports in `exports/` (91-168 KB each, 2x scale for retina)
- 60-row ticket price dataset compiled from 8+ free sources
- CPI data covering 1967-2026 (2026 is estimated at 330.0)
- GitHub repo initialized and pushed to remote

## Active Work
- Standardized article attribution preface across all research projects
- Added `## Article Attribution` section to global `C:\Users\ghigh\.claude\CLAUDE.md` (lines 47-55)
- Template uses dynamic model detection — Claude inserts its current model name at draft time

## Key Design Decisions
- **Two outputs**: Medium article (static PNGs) + Jupyter notebook (interactive Plotly, shareable on GitHub/nbviewer)
- **Histograms**: Simulated log-normal distributions using midpoint of low/high as log_mean anchor, soft filtering instead of hard clipping (avoids artificial spikes at boundaries)
- **Data sources**: Casino.org, TickPick, Yahoo Sports, Marco News/USA TODAY, Barry's Tickets, CBS News, GOBankingRates, InvestorPlace for tickets; BLS CPI-U for inflation
- **Inflation method**: `adjusted = nominal * (cpi_2025 / cpi_year)` using CPI-U annual averages, target year 2025 (CPI=321.9)
- **Visualization library**: Plotly 6.5.2 with `plotly_white` template, colorblind-safe palette, 2x scale PNG exports via kaleido
- **Annotation rendering**: Avoid `$` characters and `<br>` tags in Plotly annotations for static PNG export — they render as garbled text. Use plain text and commas instead.
- **Educational approach**: Markdown tip cells between charts covering data quality, visualization design, statistical caveats, Medium publishing tips
- **User preference captured**: Always list sites for approval before fetching (see `tasks/lessons.md`)
- **Attribution convention**: Global CLAUDE.md now mandates an attribution preface in all research article drafts, with dynamic model name insertion

## Recent Changes (this session)
- Added `## Article Attribution` section to global `C:\Users\ghigh\.claude\CLAUDE.md`
- Verified existing `article/medium_draft.md` line 5 matches the canonical attribution template

## Blockers / Open Questions
- **No blockers.** Project is feature-complete.
- Pooled histogram (Chart 3b) has slightly crowded Median/Mean annotations — cosmetic only, content is correct
- SB LX (2026) data verified by user as accurate (Seahawks 29-13 over Patriots)

## Next Steps
1. User reviews Medium draft and customizes narrative voice
2. Verify notebook renders on nbviewer (Plotly charts need saved cell outputs — notebook was executed with nbconvert so outputs are embedded)
3. Upload PNGs to Medium and publish
4. Optional polish: separate Median/Mean annotations in pooled histogram, add more annotations to other charts

## Environment
- Platform: Windows (win32), Python 3.8.0 (32-bit) at E:\Python\Python38-32
- Working directory: G:\ai\superbowl_seat_prices
- Key packages: plotly 6.5.2, pandas 2.0.3, numpy 1.24.3, scipy 1.9.1, kaleido 1.2.0
- numpy DLL warning (harmless): "loaded more than 1 DLL from .libs"
- kaleido deprecation warning (harmless): "Support for Kaleido versions less than 1.0.0 is deprecated"
