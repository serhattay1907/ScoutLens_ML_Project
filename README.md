# ⚽ ScoutLens — Football Scouting & Valuation Tool

> AI-powered scouting dashboard built on 32,000+ Transfermarkt players

**[🔴 Live Demo](https://serhattay1907.github.io/ScoutLens_ML_Project/)**

---

## Overview

ScoutLens analyzes real football data to identify undervalued players using machine learning. It combines market valuation regression with unsupervised clustering to produce a scout-friendly interface.

## Features

- 2,000 top players from Transfermarkt (2022–2025 seasons)
- XGBoost regression → predicted market value
- KMeans k=4 clustering → player archetypes (Marksman · Playmaker · Engine · Wall)
- Value gap analysis: undervalued vs overvalued
- Percentile radar charts vs same-position peers
- Filter by position, archetype, league tier, age range

## Data Pipeline
4 CSV files (Transfermarkt)
↓
Merge & clean (pandas)
↓
Feature engineering — goals/90, assists/90, league tier, age factor
↓
XGBoost regression → predicted_value
↓
KMeans (k=4) → archetypes
↓
Value gap = predicted − market value
↓
Top 2,000 players → embedded in single HTML app

## Stack

| Layer | Tools |
|---|---|
| Data processing | Python, pandas, NumPy |
| ML | scikit-learn, XGBoost |
| Development | Google Colab |
| Frontend | Vanilla HTML / CSS / JS |
| Hosting | GitHub Pages |

## Dataset

[Transfermarkt dataset](https://www.kaggle.com/datasets/davidcariboo/player-scores) — players, appearances, clubs, valuations

## Run Locally

```bash
# Just open the file — no server needed
open index.html
```

Or clone and run the notebook:
```bash
git clone https://github.com/serhattay1907/ScoutLens_ML_Project
# Open V1_football_valuation.ipynb in Google Colab
```

## Project Structure
├── index.html                   # Full app (data embedded)
├── V1_football_valuation.ipynb  # Data pipeline & ML notebook
└── README.md


<img width="1843" height="692" alt="ScoutLens_UI1" src="https://github.com/user-attachments/assets/9b1f7be0-1bed-4c35-bb8d-23d7393df981" />
<img width="359" height="851" alt="ScoutLens_UI2_Dashboard" src="https://github.com/user-attachments/assets/540c9ae0-32f8-49eb-a360-de22f25a6e8a" />



