# 🏆 2026 World Cup Predictor

A simple Python tool that uses the **Poisson Distribution** to predict 2026 World Cup matches by combining tournament match results and FIFA rankings.

---

## 🚀 How It Works

* **Base Scoring Average:** Calculates the average goals scored per match using the actual tournament matches played so far.
* **Team Strength:** Determines team strengths using official FIFA ranking points.
* **Match Simulation:** Uses the Poisson distribution to calculate the probabilities for wins, losses, or draws, finding the most likely exact scoreline.
* **Knockout Stage:** Automatically handles lower scoring trends, extra time, and penalty shootouts for playoff matches.

---

## 📁 Required Files

Place these two CSV files inside a data directory.
1. `data/matches.csv` (Must contain: `team_1`, `team_2`, `score_1`, `score_2`)
2. `data/ranking.csv` (Must contain: `Country_EN`, `Points`)

---

## 🛠️ Quick Start

```python
import pandas as pd

# 1. Load data
matches_df = pd.read_csv('data/matches.csv')
rankings_df = pd.read_csv('data/ranking.csv')

# 2. Train model
model = PoissonModel()
model.fit(matches_df, rankings_df)

# 3. Predict
prediction = model.predict('Spain', 'Argentina', is_knockout=True)
print(f"Winner: {prediction['winner']}")

📊 Requirements
* **numpy**
* **pandas**
* **scipy**
