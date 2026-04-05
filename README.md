# 🏏 IPL 2026 Winner Prediction — Machine Learning Project

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Random%20Forest-green)
![Accuracy](https://img.shields.io/badge/Accuracy-76.64%25-brightgreen)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)

---

## 📌 Project Overview

This project predicts the **IPL 2026 winner** using Machine Learning trained on **17 years of IPL data (2008–2026)**. The model analyses historical match results, team form, head-to-head records and venue statistics to generate win probabilities for all 10 teams.


---

## 🏆 Current Prediction

| Rank | Team | Win Probability | Playoff |
|------|------|----------------|---------|
| 🥇 1 | Royal Challengers Bengaluru | 75.28% | ✅ Yes |
| 🥈 2 | Kolkata Knight Riders | 64.89% | ✅ Yes |
| 🥉 3 | Rajasthan Royals | 59.11% | ✅ Yes |
| 4 | Sunrisers Hyderabad | 56.22% | ✅ Yes |
| 5 | Delhi Capitals | 54.89% | ❌ No |
| 6 | Punjab Kings | 52.06% | ❌ No |
| 7 | Lucknow Super Giants | 42.56% | ❌ No |
| 8 | Chennai Super Kings | 37.00% | ❌ No |
| 9 | Mumbai Indians | 34.78% | ❌ No |
| 10 | Gujarat Titans | 23.22% | ❌ No |

> Last updated: April 2026

---

## 📊 Dashboard Preview

> Power BI dashboard showing win probabilities, team rankings and playoff qualifications.

*<img width="1437" height="816" alt="IPL_2026_Prediction" src="https://github.com/user-attachments/assets/4d5336b2-7323-4d1d-8490-97d725ec2f6d" />*

---

## 🗂️ Project Structure

```
IPL-2026-Winner-Prediction/
│
├── data/
│   ├── raw/
│   │   └── ipl_csv2/              ← Cricsheet ball-by-ball CSVs (2008–2026)
│   └── processed/
│       ├── ipl_master.csv         ← Merged and cleaned master dataset
│       ├── ipl_features.csv       ← Engineered feature set
│       └── ipl_2026_powerbi.csv   ← Power BI source data
│
├── models/
│   └── rf_model.pkl               ← Saved Random Forest model
│
├── notebooks/
│   ├── 01_data_collection.ipynb   ← Download and merge Cricsheet data
│   ├── 02_feature_engineering.ipynb ← Build ML features
│   └── 03_modelling.ipynb         ← Train models and generate predictions
│
├── dashboard/
│   └── IPL_2026_Prediction.pbix   ← Power BI dashboard file
│
└── README.md
```

---

## ⚙️ How It Works

### Step 1 — Data Collection
- Downloaded **1,173 IPL matches** (2008–2025) from [Cricsheet.org](https://cricsheet.org)
- Merged ball-by-ball CSVs with match info CSVs into a single master dataset
- Standardised team names across seasons (e.g. Delhi Daredevils → Delhi Capitals)
- Total dataset: **279,586 rows × 37 columns**

### Step 2 — Feature Engineering
Built 12 features for every match:

| Feature | Description |
|---------|-------------|
| `team1_win_rate` | Historical win rate of team1 |
| `team2_win_rate` | Historical win rate of team2 |
| `win_rate_diff` | Difference in win rates |
| `team1_recent_form` | Wins in last 5 matches (team1) |
| `team2_recent_form` | Wins in last 5 matches (team2) |
| `form_diff` | Difference in recent form |
| `team1_h2h_wins` | Head-to-head wins (team1 vs team2) |
| `team1_venue_win_rate` | Team1 win rate at match venue |
| `team2_venue_win_rate` | Team2 win rate at match venue |
| `venue_win_rate_diff` | Difference in venue win rates |
| `toss_winner_won` | Did toss winner win the match? |
| `toss_decision_encoded` | Bat (0) or Field (1) |

### Step 3 — Model Training
Trained and compared 3 ML models:

| Model | Accuracy |
|-------|----------|
| 🥇 Random Forest | **76.64%** |
| XGBoost | 75.50% |
| Logistic Regression | 74.07% |

**Random Forest** was selected as the final model with **76.64% accuracy** on test data.

### Step 4 — Tournament Simulation
- Generated all 45 possible matchups between 10 teams
- Used `predict_proba()` to get win probability for each matchup
- Averaged win probabilities across all matchups per team
- Final output: win probability ranking for all 10 teams

---


## 🛠️ Tech Stack

| Tool | Usage |
|------|-------|
| Python 3.10 | Core programming language |
| Pandas | Data manipulation and cleaning |
| Scikit-learn | ML models (Logistic Regression, Random Forest) |
| XGBoost | Gradient boosting model |
| Joblib | Saving and loading trained models |
| BeautifulSoup | Web scraping live 2026 results |
| Power BI | Interactive dashboard |
| Jupyter Notebook | Development environment |

---

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/vineet1595/ipl-2026-winner-prediction.git

# Navigate to project folder
cd ipl-2026-winner-prediction

# Install required libraries
pip install pandas scikit-learn xgboost joblib requests beautifulsoup4 tqdm
```

---

## 🚀 How to Run

```bash
# Step 1 — Open Jupyter Notebook
jupyter notebook

# Step 2 — Run notebooks in order
# 01_data_collection.ipynb
# 02_feature_engineering.ipynb
# 03_modelling.ipynb

# Step 3 — Update with latest 2026 results
python src/update_2026.py
```

---

## 📈 Data Source

| Source | Data |
|--------|------|
| [Cricsheet.org](https://cricsheet.org/downloads/) | Ball-by-ball IPL data 2008–2025 |

---

## 🙋 About Me

**Vineet Mahajan**
Junior Data Analyst at Tata Consultancy Services (TCS), Mumbai
Specialising in Power BI, DAX, SQL and Python

📌 This project is part of my Data Science portfolio

---

## 📬 Connect

- 💼 LinkedIn: [(https://linkedin.com/in/vm62)]
- 🐙 GitHub: [https://github.com/vineet1595]

---

## ⚠️ Disclaimer

This project is built purely for educational and portfolio purposes.
Predictions are based on historical data and ML models — not guaranteed outcomes.
Cricket is inherently unpredictable and upsets are always possible! 🏏
