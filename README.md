# 🎵 Spotify Hit Song Predictor

A machine learning project that predicts whether a song will be a "hit" or a "flop" using only its Spotify audio features — danceability, energy, loudness, and more.

## 📌 Overview
This project explores whether a song's audio characteristics alone can predict its commercial success (measured by chart appearance). It combines exploratory data analysis, statistical correlation, and two classification models to answer that question.

## 📊 Dataset
- **Source:** [Spotify Hit Predictor Dataset (1960-2019)](https://www.kaggle.com/datasets/theoverman/the-spotify-hit-predictor-dataset) on Kaggle
- **Subset used:** 2010s tracks — 6,398 songs
- **Target:** `target` — 1 = Hit, 0 = Flop (perfectly balanced: 3,199 each)
- **Features:** danceability, energy, key, loudness, mode, speechiness, acousticness, instrumentalness, liveness, valence, tempo, duration_ms, time_signature, chorus_hit, sections

## 🔍 Approach
1. **Exploratory analysis** — checked feature distributions and correlation with target
2. **Preprocessing** — dropped identifier columns (track, artist, uri), scaled features for logistic regression
3. **Modeling** — trained and compared two classifiers:
   - Logistic Regression (baseline)
   - Random Forest
4. **Evaluation** — accuracy, precision/recall, F1-score, ROC-AUC
5. **Feature importance** — identified which audio features matter most

## 📈 Results

| Model | Accuracy | ROC-AUC |
|---|---|---|
| Logistic Regression | 0.80 | 0.867 |
| Random Forest | **0.83** | **0.912** |

Random Forest outperformed Logistic Regression, suggesting the relationship between audio features and hit status involves non-linear patterns rather than a simple straight-line relationship.

## 🔑 Key Findings
- **`instrumentalness`** is the single strongest predictor (both correlation and feature importance) — vocal-heavy tracks are far more likely to become hits, while instrumental tracks rarely chart
- **`loudness`**, **`danceability`**, **`energy`**, and **`acousticness`** also meaningfully influence hit likelihood
- **`key`**, **`mode`**, and **`time_signature`** had negligible predictive power


## 🛠️ Tech Stack
`Python` · `pandas` · `numpy` · `matplotlib` · `scikit-learn` · `Google Colab`

## 🚀 How to Run
1. Clone this repository
```bash
   git clone https://github.com/ayushyadav/spotify-hit-predictor.git
```
2. Open `Spotify_Hit_Song_Predictor.ipynb` in Google Colab or Jupyter Notebook
3. Ensure `dataset-of-10s.csv` is in the same directory (or upload when prompted)
4. Run all cells

## 📁 Files
- `Spotify_Hit_Song_Predictor.ipynb` — full notebook with EDA, modeling, and evaluation
- `dataset-of-10s.csv` — dataset used
