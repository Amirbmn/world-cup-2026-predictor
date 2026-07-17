# 🏆 2026 World Cup Predictor

A simple Python tool that uses the **Poisson Distribution** to predict 2026 World Cup matches based on team strengths and FIFA rankings.

---

## 🚀 How It Works

* **Team Strength:** Calculates how strong a team is using their official FIFA ranking points.
* **Match Simulation:** Uses the Poisson distribution to calculate the most likely scoreline and probabilities for wins, losses, or draws.
* **Knockout Stage:** Automatically handles extra time and penalty shootouts if a playoff match ends in a draw



## 📁 Required Files

Place these two CSV files inside a data directory
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
```

📊 Requirements
*numpy
*pandas
*scipy
