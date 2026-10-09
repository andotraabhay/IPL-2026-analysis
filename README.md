# 🏏 IPL 2026 Season Analysis

An end-to-end exploratory data analysis (EDA) of the IPL 2026 season using **Python, Pandas, Matplotlib and Seaborn**. The project turns raw match-level and ball-by-ball data into player, team and venue insights, and explains each finding in plain language.

---

## 📌 Table of Contents
1. [Project Overview](#-project-overview)
2. [Objectives](#-objectives)
3. [Dataset](#-dataset)
4. [Tools and Technologies](#-tools-and-technologies)
5. [Methodology](#-methodology)
6. [Key Findings](#-key-findings)
7. [Visualizations](#-visualizations)
8. [Project Structure](#-project-structure)
9. [How to Run](#-how-to-run)
10. [Limitations](#-limitations)
11. [Future Improvements](#-future-improvements)
12. [Author](#-author)

---

## 📖 Project Overview

The Indian Premier League generates a huge amount of data every season. This project analyses the IPL 2026 season to answer practical questions such as:

- Who scores the runs and who takes the wickets, and how concentrated is that performance?
- Which teams scored the most on average, and how do venues affect scoring?
- Does winning the toss and choosing to bowl or bat first relate to winning the match?
- Which batting statistics move together, and is a high run total the same thing as a high strike rate?

The analysis is documented in a single Jupyter notebook (`ipl-2026-analysis.ipynb`), with code, charts and written interpretation side by side.

---

## 🎯 Objectives

- Clean and validate two related datasets (match level and ball by ball).
- Aggregate ball-by-ball data into player totals, match totals and innings totals.
- Apply the right chart for each question (distribution, comparison, relationship, correlation).
- Convert charts into written, evidence-backed insights.
- Document the limitations of the data honestly.

---

## 📂 Dataset

The analysis uses two CSV files.

**1. Match-level data** (one row per match)

| Column | Description |
|---|---|
| `match_id`, `date`, `venue`, `stage` | Match identification and location |
| `team1`, `team2` | Teams playing |
| `toss_winner`, `toss_decision` | Toss result and decision (bat or bowl) |
| `first_ings_score`, `first_ings_wkts` | First innings runs and wickets |
| `second_ings_score`, `second_ings_wkts` | Second innings runs and wickets |
| `match_result`, `match_winner`, `win_margins` | Result details |
| `player_of_the_match`, `top_scorer`, `highscore` | Standout performers |
| `best_bowling`, `best_bowling_figure` | Best bowling performance of the match |
| `super_over_match` | Whether the match went to a super over |

**2. Ball-by-ball data** (one row per delivery)

| Column | Description |
|---|---|
| `match_no`, `date`, `stage`, `venue` | Match identification |
| `batting_team`, `bowling_team`, `innings`, `over` | Context of the delivery |
| `striker`, `bowler` | Batter and bowler on the ball |
| `runs_of_bat`, `extras` | Runs scored off the bat and extras |
| `wide`, `legbyes`, `byes`, `noballs` | Types of extras |
| `wicket_type`, `player_dismissed`, `fielder` | Dismissal details |

**Source:** <add the Kaggle dataset link here>

---

## 🛠 Tools and Technologies

- **Python 3**
- **Pandas** for cleaning, filtering, `groupby` and aggregation
- **Matplotlib** for figure control (titles, sizes, label rotation)
- **Seaborn** for statistical visualisation
- **Jupyter Notebook / Kaggle Notebooks** for analysis and documentation
- **Git and GitHub** for version control

---

## 🔬 Methodology

1. **Data health check:** checked missing values and duplicates with `isnull().sum()` and `duplicated().sum()`. Missing values in `wicket_type` and `player_dismissed` are expected, because most deliveries are not wickets.
2. **Aggregation:** ball-by-ball data was grouped into player totals, match totals and innings totals using `groupby` and `.agg()`.
3. **Fair counting rules:**
   - Wides were excluded when counting balls faced by a batter.
   - Dismissals not credited to the bowler (such as run outs) were excluded from wicket counts.
   - Batters with fewer than 30 balls faced were excluded from the correlation analysis, because their strike rates are too noisy to be meaningful.
4. **Univariate analysis:** distributions of runs per batter and wickets per bowler (`histplot`).
5. **Bivariate analysis:** team scoring (`barplot`), toss versus result (`countplot` with `hue`), and venue scoring (`boxplot`).
6. **Multivariate analysis:** correlation of batter statistics (`heatmap`).
7. **Top performers:** top 10 run scorers and wicket takers (`barplot`).
8. **Interpretation:** each chart is followed by a written takeaway, and the notebook ends with a summary of insights.

---

## 🔎 Key Findings

**1. Performance is concentrated in a few players.**
Runs per batter and wickets per bowler are both strongly right-skewed. Around 95 players scored fewer than about 75 runs in the season, while only a handful passed 600. A small core of specialist batters and strike bowlers produced most of the output.

**2. Team batting output differs noticeably.**
PBKS had the highest average score per match (about 200), followed by SRH (about 195). KKR had the lowest (about 158), a gap of roughly 40 runs between the top and bottom teams.

**3. Most toss winners chose to bowl first.**
Among toss winners who chose to bowl, the toss winner went on to win 20 times and lose 14 times. Only 5 matches saw a bat-first decision (1 win, 4 losses), which is too small a sample for a firm conclusion.

**4. Venues shape scoring.**
Jaipur, Mumbai (Wankhede) and Mullanpur had the highest median innings totals, while Guwahati had the lowest (about 139). Delhi showed the widest spread, making scores there the least predictable.

**5. Scoring big and scoring fast are different skills.**
Total runs correlate almost perfectly with balls faced (0.97), mostly because of playing time. Strike rate is only moderately correlated with total runs (0.55) and is most strongly linked to six-hitting (0.72).

**6. Top performers.**
- Top run scorers: <add top 3 names and totals>
- Top wicket takers: <add top 3 names and totals>

---

## 📊 Visualizations

| Question | Chart used |
|---|---|
| How are runs and wickets distributed across players? | `histplot` |
| Which team scores the most per match? | `barplot` |
| Does the toss decision relate to winning? | `countplot` with `hue` |
| How do innings totals vary by venue? | `boxplot` |
| Which batting statistics are related? | `heatmap` of a correlation matrix |
| Who are the top performers? | Horizontal `barplot` |

All charts, along with the code that produced them, are in the notebook `ipl-2026-analysis.ipynb`.

---

## 📁 Project Structure

```
IPL-2026-analysis/
│
├── ipl-2026-analysis.ipynb   # Full analysis: code, charts and insights
└── README.md                 # Project documentation
```

---

## ▶️ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/andotraabhay/IPL-2026-analysis.git
   cd IPL-2026-analysis
   ```
2. Install the required libraries:
   ```bash
   pip install pandas matplotlib seaborn jupyter
   ```
3. Download the datasets from <add the Kaggle dataset link here> and place them where the notebook expects them (update the file paths in the first cells if needed).
4. Launch Jupyter and open the notebook:
   ```bash
   jupyter notebook ipl-2026-analysis.ipynb
   ```
5. Run all cells from top to bottom.

---

## ⚠️ Limitations

- **Small sample:** the data covers a single tournament, and some venues and teams have only a handful of innings, so patterns may not generalise.
- **Correlation is not causation:** the heatmap shows which statistics move together, not why.
- **Volume effect:** most batter statistics are raw counts, so they correlate partly because of playing time alone.
- **Possible data issues:** a few very low innings totals may come from abandoned or shortened matches and were not removed.

---

## 🚀 Future Improvements

- Use **rate metrics** (sixes per ball faced, boundary percentage, bowling economy) instead of raw counts.
- Compare **first-innings and second-innings** scores to test whether chasing teams have an advantage.
- Identify and handle abandoned or shortened matches explicitly.
- Add **SQL queries** answering the same questions on the dataset.
- Build an interactive **Power BI dashboard** from the same data.

---

## 👤 Author

**Abhay Singh Rajput**
Final-year Mechanical Engineering student at MVJ College of Engineering, Bangalore, building a career in data analytics and AI.

- GitHub: [andotraabhay](https://github.com/andotraabhay)
- Kaggle: [AbhaySinghRajput1111](https://www.kaggle.com/AbhaySinghRajput1111)

⭐ If you found this project useful, consider giving the repository a star.
