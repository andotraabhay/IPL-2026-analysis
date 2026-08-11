# IPL 2026 Season Analysis

A data analysis project exploring team performance, batting, and bowling trends from the IPL 2026 season using Python and Pandas.

## Dataset

Source: [IPL 2026 Dataset on Kaggle](https://www.kaggle.com/datasets/abhaysinghrajput1111/ipl-2026-dataset)

| File | Rows | Columns | Description |
|---|---|---|---|
| `matches.csv` | 39 | 23 | Match-level data — teams, venue, toss, result, player of the match |
| `deliveries.csv` | 17,477 | 19 | Ball-by-ball data — runs, extras, wickets, batter/bowler per delivery |

## Tools Used

- Python
- Pandas
- Matplotlib

## Objective

To explore the 2026 IPL season and answer questions like:
- Which teams and players performed best this season?
- Does winning the toss — and the decision to bat or bowl — actually affect match outcomes?
- Who were the standout batters and bowlers by volume and efficiency?

## Project Steps

1. **Setup** — Load `matches.csv` and `deliveries.csv`
2. **Data Cleaning** — Convert date columns, fix score dtypes, handle missing values, check duplicates
3. **Matches Analysis** — Wins per team, toss impact, venues, stages, win margins, player of the match
4. **Batting Analysis** — Runs, strike rate, batting average, boundary percentage per batter
5. **Bowling Analysis** — Runs conceded, economy rate, bowling average, strike rate, wickets per bowler
6. **Visualization** — Charts for all of the above using Matplotlib
7. **Conclusion** — Summary of key findings

## Key Findings

- **Toss & chasing:** Teams chose to bowl first after winning the toss in 34 of 39 matches (~87%). Bowling first led to a win 58.8% of the time, versus only 20% for batting first — chasing was clearly the stronger strategy this season.
- **Most wins:** RCB and PBKS led the season with 6 wins each.
- **Top run-scorer:** Vaibhav Sooryavanshi, with 776 runs.
- **Most wickets:** Bhuvneshwar Kumar, Jofra Archer, and Kagiso Rabada tied at 29 wickets each.
- **Best economy (min. 10 overs bowled):** Sunil Narine, at 6.60.

## How to Run

1. Open the notebook on Kaggle (link below) or clone this repo.
2. If running locally, install dependencies: `pip install pandas matplotlib`.
3. Run all cells in order — the notebook follows the 7-step structure above.

## Notebook

[View the full notebook on Kaggle](https://www.kaggle.com/code/abhaysinghrajput1111/ipl-2026-analysis)
