# Data Sources

## Ticket Price Data (`superbowl_ticket_prices.csv`)

Primary sources cross-referenced:
- **Casino.org** - "Trendspotting: Average Super Bowl Ticket Prices Over The Years (1967-2024)" - Primary for early-era face values
- **TickPick** - "History of Super Bowl Ticket Prices" - Primary for resale market data (2019-2026) and face value tier breakdowns
- **Marco News / USA TODAY Network** - Year-by-year averages, dates, stadiums, winners, scores, attendance for all 60 Super Bowls
- **Yahoo Sports** - Face value confirmation for every Super Bowl, inflation-adjusted cross-checks
- **Barry's Tickets** - Secondary market trends 2020-2025
- **Fan Hospitality** - Detailed 2010 and 2014 face value tiers
- **CBS News** - 2026 resale market data
- **InvestorPlace** - 2019-2024 resale averages
- **GOBankingRates** - Inflation-adjusted values for cross-checking
- **Bleacher Report** - Ranking of all SB average prices

## Known Discrepancies

1. **SB I face value**: Sources vary between $6 (low tier) and $12 (high tier). Used $6/$12.
2. **SB XIX (1985)**: Most sources say $60; some cite $125 premium tier. Used $60 as high.
3. **SB XXX (1996)**: Confirmed $200-$350 range - first year with significant tier spread.
4. **SB LIV-LV (2020-2021)**: Face values jumped significantly. Verified across multiple sources.
5. **SB LVI (2022)**: Face value range $950-$7,124 confirmed by TickPick tier breakdown.
6. **Recent avg_ticket_price (2022+)**: Conflates face value and market averages in some sources. The CSV uses the most commonly cited "average" from primary sources.

## CPI Data (`cpi_annual_averages.csv`)

- **Source**: BLS CPI-U (Consumer Price Index for All Urban Consumers), annual averages
- **Base period**: 1982-1984 = 100
- **Cross-referenced with**: Minneapolis Fed CPI historical tables, US Inflation Calculator
- **Coverage**: 1967-2025
- **Adjustment target**: 2025 (CPI = 321.9)

## Data Collection Date
- February 8, 2026
