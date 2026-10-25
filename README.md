# ⚽ ScoutLens — ML-Based Football Player Valuation & Undervalued Talent Discovery

Predicts a player's fair market value from performance data and surfaces **undervalued players** — with a deliberate focus on talent outside the top leagues.

**🔴 Live demos:** [V2 — ML valuation app](https://serhattay1907.github.io/ScoutLens_ML_Project/scoutlens_ml_valuation.html) · [V1 — scouting dashboard](https://serhattay1907.github.io/ScoutLens_ML_Project/)

---

## 📊 Results (V2)
| Metric | Value |
|---|---|
| Raw player records | 47,701 (Transfermarkt, 6 CSVs) |
| Active players modelled | 6,952 |
| Best model | **XGBoost — R² 0.677** (log scale, CV) |
| Runner-ups | LightGBM 0.649 · Random Forest 0.645 |
| Improvement over V1 baseline | R² 0.047 → **0.677** |
| MAE | ≈ €3.1M |
| Top-30 undervalued list | 60% from Tier 2–3 leagues (target ≥ 60% ✅) |

## 🧠 Pipeline
```
6 Transfermarkt CSVs (47.7K players)
  → active-player filter (6,952)
  → feature engineering: per-90 stats, performance trend, transfer history, league tier, age
  → model competition: XGBoost vs LightGBM vs Random Forest (CV)
  → position-based KMeans → 15 player archetypes
  → value gap (log scale) = predicted − market value
  → Top-30 undervalued + "Future Gems" growth model
  → interactive HTML app
```

**Key decisions**
- **Log-scale value gap** instead of raw % — prevents cheap players dominating the list
- **€100K market-value floor** to remove noise from inactive/amateur records
- **Dropped "highest market value"** as a feature — it leaks the target
- **Position-specific clustering** so archetypes compare like with like

## 🖥️ App features (V2)
Player Scout · Future Gems · Compare Players · Pipeline view · **AI Analyst** (Claude API, bring-your-own key — the key stays in your browser)

## 🛠️ Stack
Python · pandas · NumPy · scikit-learn · XGBoost · LightGBM · KMeans · Matplotlib · Google Colab · HTML/CSS/JS · GitHub Pages

## 📁 Files
| File | Purpose |
|---|---|
| `ScoutLens_V2_ml_based_player_valuation.ipynb` | V2 pipeline (stages 1–9) |
| `scoutlens_ml_valuation.html` | V2 interactive app |
| `V1_football_valuation.ipynb` / `.py` | V1 baseline pipeline |
| `index.html` | V1 scouting dashboard (KMeans archetypes, radar charts) |

## 📦 Data
[Transfermarkt dataset on Kaggle](https://www.kaggle.com/datasets/davidcariboo/player-scores) — players, appearances, clubs, valuations, transfers.

## ▶️ Run
Open either HTML file in a browser (data is embedded), or open the notebooks in Google Colab.

---
**Author:** Serhat Tay

<img width="1843" height="692" alt="ScoutLens UI" src="https://github.com/user-attachments/assets/9b1f7be0-1bed-4c35-bb8d-23d7393df981" />
<img width="359" height="851" alt="ScoutLens dashboard" src="https://github.com/user-attachments/assets/540c9ae0-32f8-49eb-a360-de22f25a6e8a" />
