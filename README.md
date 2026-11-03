# IPL Cricket Match Performance Analysis (2008–2019)

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR-GITHUB-USERNAME/ipl-cricket-match-analysis/blob/main/IPL_Cricket_Match_Analysis.ipynb)

A data analysis of 12 seasons of Indian Premier League batting records (756 matches, 11,546 batting rows), written in Python. It cleans the raw scorecard data, then looks at players, dismissals and teams, and ends with a one-page summary of what the data shows. This is project 5 of a data analyst training programme.

![Batting performance at a glance](outputs/ipl_key_insights.png)

## What the notebook covers

| Objective | Tasks |
|---|---|
| **1. Understand the IPL data** | Matches, teams and players · missing and duplicate information · inconsistent data · scoring patterns (EDA) |
| **2. Analyse player performance** | Top run scorers · strike rate and efficiency · fours and sixes · captains and wicket keepers |
| **3. Analyse scoring and dismissals** | Dismissal patterns · key bowlers and fielders · not-out vs dismissed · outliers |
| **4. Generate overall insights** | Team comparison · strong and weak batters · runs, balls, boundaries and strike rate · summary dashboard |

## Key findings

- **Scoring has risen.** Runs off the bat per innings went from 147 in 2008 to 157 in 2019, and sixes per 100 balls from 4.8 to 5.6, while fours stayed near 12.
- **Runs are concentrated.** The top 10 batters scored 21% of all runs and the top 50 scored 61%. V Kohli leads with 5,412 runs, then SK Raina (5,368).
- **Caught is the main way out** (63% of dismissals). Run outs fell from 12.3% of dismissals in 2008 to 6.0% in 2019.
- **Boundaries and strike rate move together** (r = 0.88 across innings of 10+ balls). Part of that link is built in, because boundaries are runs.
- **Teams.** Chennai Super Kings have the best net run difference (+6.6 runs per innings), then Mumbai Indians (+3.6). Batting first averages 154 runs against 143 when chasing, because chasing sides stop at the target.
- **Strong batters** (top quarter on a performance index of average, strike rate and 30+ starts) include AD Russell, RR Pant and DA Warner.

The full list of 9 insights is in `outputs/ipl_key_insights.csv`.

## Repository layout

```
├── IPL_Cricket_Match_Analysis.ipynb   the analysis (all four objectives)
├── data/ipl_batting.csv               raw data, one row per batter per match
├── outputs/                           charts and tables the notebook saves
├── requirements.txt
└── README.md
```

## How to run

**In Google Colab:** click the badge above, upload `data/ipl_batting.csv` to the Colab file panel (next to the notebook), then choose *Runtime → Run all*.

**On your computer:**

```bash
git clone https://github.com/YOUR-GITHUB-USERNAME/ipl-cricket-match-analysis.git
cd ipl-cricket-match-analysis
pip install -r requirements.txt
jupyter notebook IPL_Cricket_Match_Analysis.ipynb
```

Run all cells from the top. Everything the notebook saves goes into `outputs/`. It runs in under a minute and was tested with pandas 2.2 and pandas 3.0.

## Things to know before using the numbers

- **The file does not say which team a batter played for.** The batting team is derived from the row order and from the bowlers and fielders named in each dismissal. It agrees with each batter's usual team for that season in 99.9% of rows.
- **Team totals are runs off the bat.** Extras are not in the file, and neither are match results, overs bowled or runs conceded by bowlers. "Net runs per innings" is therefore a rough guide to strength, not a win–loss record, and bowlers can only be ranked by wickets.
- **Rain-shortened matches** (35 of 756) are left out of the team comparisons, but every batter statistic uses all innings.
- **Small teams** (Gujarat Lions, Rising Pune Supergiant, Kochi Tuskers Kerala; under 40 innings) appear in tables but are never named best or weakest.
- **"Weak" is relative.** It means lowest among the 92 batters with 500+ balls faced, and can include bowlers and lower-order batters.
- Bowler and fielder names in the file are often surnames only, so ambiguous ones (for example Singh, Sharma) are excluded from rankings or marked.
- Delhi Daredevils and Delhi Capitals are treated as one team.

## Data

`data/ipl_batting.csv` was supplied with the training project (17 columns: match, teams, batter, runs, balls, minutes, fours, sixes, strike rate, role, how out, bowler, fielder, date). Check you are allowed to share it before making this repository public.

## Tools

Python · pandas · NumPy · matplotlib · seaborn · SciPy
