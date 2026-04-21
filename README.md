# High-Speed Running Decay Across Match Halves in a domestic African Football League

*GPS-based physical performance analysis | 2024/25 season*

---

## What this project is

This analysis quantifies second-half high-speed running (HSR) decay in a domestic African football league using GPS tracking data collected across a full season. It covers all clubs in the league across up to 30 match days per club, producing  the first GPS-based physical performance benchmark for football at this level.

The questions driving the work:

1. Do outfield players run significantly less at high speed in the second half?
2. Does decay vary by position?
3. Does match outcome influence second-half physical output?
4. How much do clubs differ from each other in decay magnitude?

The full write-up with context, methodology, and discussion is on Substack: [link]

---

## Key findings

| Metric | Value |
|--------|-------|
| Total observations | 3,441 player-match pairs |
| Mean HSR rate — 1st half | 10.80 m/min |
| Mean HSR rate — 2nd half | 8.11 m/min |
| Mean absolute decay | 2.69 m/min (24.9%) |
| Clubs with significant decay | 16 / 16 |
| Ratio between highest and lowest decay club | 3.8x |

**By position:**

| Position | Decay (m/min) | Decay (%) |
|----------|--------------|-----------|
| Defenders | 1.98 | 12.8% |
| Midfielders | 2.95 | 22.9% |
| Forwards | 3.60 | 23.9% |

Match outcome had no significant effect on decay magnitude.

---

## Metric

**HSR Rate** = (distance in speed zones above 18 km/h) / half duration in minutes

Using a rate rather than raw distance normalises for players with different half durations and makes the within-player comparison fair regardless of substitution timing.

---

## Methods

- Overall decay: paired t-test + Wilcoxon signed-rank (n = 3,441 paired observations)
- Positional variation: one-way ANOVA + Tukey HSD post-hoc
- Outcome variation: one-way ANOVA
- Club-level: per-club paired t-tests sorted by mean decay
- Stack: Python — pandas, scipy, matplotlib

---

## Repository structure

```
upl-hsr-decay/
├─ notebooks/
 ├── 01_data_audit.ipynb       # Completeness checks, distribution review
 ├── 02_cleaning.ipynb         # Filtering logic, HSR rate calculation
 ├── 03_analysis.ipynb         # All statistical tests and summaries
 └── 04_visualisations.ipynb   # Chart generation, dual theme output

```

The raw GPS data is not included; access to full-season multi-club tracking data from the  league is not publicly available. The notebooks document the full pipeline from raw export to final figures. If you work with GPS data from Catapult One or similar systems, the cleaning and analysis logic is directly transferable to your own exports.

---

## References

Aughey, R. (2010). Australian football player work rate: evidence of fatigue and pacing? *International Journal of Sports Physiology and Performance, 5*(3), 394–405.

Mäkiniemi, J. K., Savolainen, E. H., Finni, T., & Ihalainen, J. (2022). Position specific physical demands in different phases of competitive matches in national level women's football. *Biology of Sport, 40*, 629–637.

Thoseby, B., Govus, A., Clarke, A., Middleton, K., & Dascombe, B. (2022). Positional and temporal differences in peak match running demands of elite football. *Biology of Sport, 40*, 311–319.

Van de Casteele, F., Deprez, D., Van Haaren, J., Derave, W., & Lievens, E. (2023). In professional football the decline in high-intensity running activities from first to second half is more pronounced in players with a fast muscle typology. *Scandinavian Journal of Medicine and Science in Sports, 34*.

---

**Humphrey Nyanzi**  
Sports Scientist & Data Analyst   
[GitHub](https://github.com/humphrey-nyanzi) · [Substack](https://humphreyn-substack.com) · [X](https://x.com/phreyn)
