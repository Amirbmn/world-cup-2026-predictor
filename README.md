# 🏆 2026 World Cup Predictor

A lightweight statistical model based on the **Poisson Distribution** to predict the outcomes of the 2026 World Cup matches using team strengths and FIFA rankings.

---

## 🚀 Features

* **Data-Driven Fitting:** Computes average tournament goals and relative team strengths directly from input datasets.
* **Probability Matrix Simulation:** Calculates the exact probabilities for wins, losses, and draws by simulating goal matrices .
* **Knockout Stage Support:** Accounts for defensive knockout dynamics, extra-time goal probabilities, and penalty shootout coin-flips.

---

## 📁 Data Structure

The project expects two CSV files located in data directory
1. **`data/matches.csv`**: Historical match results with columns: `team_1`, `team_2`, `score_1`, `score_2`
2. **`data/ranking.csv`**: Official FIFA points with columns: `Country_EN`, `Points`

---

## 🛠️ Quick Start

```python
import pandas as pd

# 1. Load your datasets
matches_df = pd.read_csv('data/matches.csv')
rankings_df = pd.read_csv('data/ranking.csv')

# 2. Initialize and fit the model
model = PoissonModel()
model.fit(matches_df, rankings_df)

# 3. Predict a knockout match
prediction = model.predict('Spain', 'Argentina', is_knockout=True)
print(f"Winner: {prediction['winner']}")
