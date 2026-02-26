# High Speed Running (HSR) Decay in the Uganda Premier League

**Season:** 2024/25 UPL  
**Data:** Catapult GPS (Catapult One)  
**Author:** Humphrey Nyanzi

## Project Structure

```
upl-hsr-decay/
├── data/
│   ├── raw/              # Original Catapult exports — do not modify
│   └── processed/        # Cleaned, merged, analysis-ready files
├── notebooks/
│   ├── 01_data_audit.ipynb       # Sanity checks, completeness, distributions
│   ├── 02_cleaning.ipynb         # Filtering, parsing, feature engineering
│   ├── 03_analysis.ipynb         # Statistical tests (paired t, ANOVA)
│   └── 04_visualizations.ipynb   # All final charts and figures
├── outputs/
│   ├── figures/          # Saved plots (.png)
│   └── tables/           # Summary stats, test results (.csv)
├── docs/
│   └── project_brief.docx
└── README.md
```

## Notebooks (run in order)

1. **01_data_audit** — load raw data, check completeness, flag issues
2. **02_cleaning** — apply inclusion criteria, parse position/outcome, calculate HSR_rate
3. **03_analysis** — paired t-test (decay), ANOVA by position, ANOVA by outcome
4. **04_visualizations** — boxplots, bar charts, summary visuals for FUFA and portfolio

## Key Decisions

- Metric: HSR Rate = (SZ4_km + SZ5_km) * 1000 / (duration_s / 60)
- Exclusions: Goalkeepers, players with < 35 min in either half
- Positions: DEF, MID, FWD (parsed from GPS session tags)
- Outcome: WIN / DRAW / LOSS (parsed from session title string)
