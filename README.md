# Decoding the 2026 Tamil Nadu Election
### A Data-Driven Story Pitch for AtliQ Media

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.0-green)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.8-orange)
![ECI Data](https://img.shields.io/badge/Source-ECI%20Data-red)
![Codebasics](https://img.shields.io/badge/Challenge-Codebasics%20RPC%2026-purple)

---

## Project Overview

AtliQ Media is producing a one-hour fact-based TV show on the 2026 Tamil Nadu Assembly election results. Unlike most channels covering the election with debates and political commentary, AtliQ wants the opposite — a clean, data-driven show grounded only in ECI data.

As the data analyst on this project, I analyzed all 234 constituencies from the 2026 Tamil Nadu Assembly election, selected 3 compelling data stories, and built a stakeholder pitch deck for AtliQ Media's content team.

**This is a non-partisan exercise using only publicly available Election Commission of India data. No political inference is drawn.**

---

## The Three Stories

### Story 1 — The Map Redrawn
163 of 234 seats changed party hands in a single election — a 70% churn rate. A brand new party (TVK) won 108 seats in its very first election, drawing seats from every single party simultaneously.

### Story 2 — The Wave Hit Unevenly
Chennai Metro saw 94% of seats flip — the highest in the state. But the Delta region held steadiest at 45%. The wave was real, but far from uniform across Tamil Nadu's six regions.

### Story 3 — The Illusion of Decisive Wins
In 2021, only 2 winners got less than 35% of the vote in their constituency. In 2026, 64 did. Average margins collapsed from 11.7% to 7.7%. One seat was decided by a margin of exactly 1 vote.

---

## Key Numbers at a Glance

| Metric | 2021 | 2026 |
|---|---|---|
| Seats that changed party | — | 163 of 234 (70%) |
| TVK seats | 0 | 108 |
| DMK seats | 133 | 59 |
| AIADMK seats | 66 | 47 |
| Average winning margin | 11.7% | 7.7% |
| Winners with less than 35% vote share | 2 | 64 |
| Narrowest margin | — | 1 vote |

---

## Repository Structure

```
tn-election-2026/
│
├── data/
│   └── raw/
│       ├── tn_2021_results.csv          # Candidate-level 2021 results (4,232 rows)
│       ├── tn_2026_results.csv          # Candidate-level 2026 results (4,257 rows)
│       └── constituency_master.csv      # 234 constituencies with region mapping
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb           # Data audit, cleaning, master table build
│   └── 02_charts.ipynb                  # All 5 charts with explanations
│
├── charts/
│   ├── chart1_seat_comparison.png       # Seats won by party 2021 vs 2026
│   ├── chart2_flip_flows.png            # Where did the 163 flipped seats go
│   ├── chart3_regional_flips.png        # Flip rate by region
│   ├── chart4_margin_distribution.png   # Margin distribution 2021 vs 2026
│   └── chart5_vote_share_scatter.png    # 64 winners with less than 35% vote share
│
└── Decoding-the-2026-Tamil-Nadu-Election.pdf   # Full stakeholder pitch deck
```

---

## Data Sources

| File | Source | Description |
|---|---|---|
| tn_2026_results.csv | ECI live results portal (results.eci.gov.in) | 2026 candidate-level results |
| tn_2021_results.csv | Trivedi Centre for Political Data, Ashoka University | 2021 candidate-level results |
| constituency_master.csv | Codebasics Challenge Pack | 234 constituency master reference |

**Note:** ECI Form-20 (final audited data) had not been released when this dataset was prepared. All findings are based on the live results portal and are directionally accurate.

---

## Tools Used

- **Python 3.12** — Data cleaning and analysis
- **Pandas** — Data manipulation and joins
- **Matplotlib** — Chart generation
- **Canva** — Pitch deck design
- **Jupyter Notebook** — Analysis environment

---

## Key Technical Decisions

**Why ac_number and not constituency name for joins?**
Constituency names are spelled differently across the 2021 and 2026 files (e.g. Gummidipundi vs Gummidipoondi). Joining on text names would have caused silent data loss for 34 constituencies. The official ECI ac_number was used as the primary join key instead.

**How were winners identified?**
Each constituency has multiple rows — one per candidate. Winners were identified by selecting the candidate with the maximum votes per ac_number using idxmax(). Vote share was calculated by dividing winner votes by total valid votes per constituency.

**How were margins calculated?**
The top 2 candidates per constituency were extracted after sorting by votes descending. Margin = first place votes minus second place votes. Margin percentage = margin divided by total valid votes.

---

## Pitch Deck

The full 10-slide stakeholder deck is available in the repo:
**Decoding-the-2026-Tamil-Nadu-Election.pdf**

Slides covered:
1. Cover
2. The Assignment
3. Story 1 — The Map Redrawn
4. Story 1 — Where Did the Seats Go
5. Story 2 — The Wave Hit Unevenly
6. Story 2 — Seats Flipped by Region
7. Story 3 — The Illusion of Decisive Wins
8. Story 3 — Margin Collapse 2021 vs 2026
9. Honest About the Data
10. Three Headlines for AtliQ Media

---

## Data Limitations

1. **2026 turnout unavailable** — ECI Form-20 had not been released at time of analysis
2. **Name spelling differences** — Joined on ac_number to avoid silent data loss
3. **Live results source** — Minor revisions possible in final audited data
4. **Non-partisan** — No political inference drawn from any finding

---

## About This Project

This project was completed as part of the **Codebasics Resume Project Challenge #26**.

**Shubham Jaiswal | Data Analyst**
Open to remote data analyst roles

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](www.linkedin.com/in/iam-shubhamjaiswal)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black)](https://github.com/JaiswalAnalytics)
