# Project: Predicting All-NBA Team Selections

## Dataset

- **Source:** [NBA Player Stats (1950–2017)](https://www.kaggle.com/datasets/drgilermo/nba-players-stats?resource=download&select=Seasons_Stats.csv)  
- **File used:** `Seasons_Stats.csv`  
- **Size:** 24,000+ player-season rows  
- **Filtering:** Removed players with fewer than 15 minutes per game to eliminate bench players

## Goal

Predict whether a player will be selected to an All-NBA team (First, Second, or Third) based on their season stats.

## Classification Task

- **Target:** `is_all_nba` (binary classification)
- **Features Used:**
  - Points, assists, rebounds, steals, blocks, minutes played
  - Shooting percentages (FG%, 3P%, FT%
  - Advanced stats: PER, WS, WS/48, BPM, VORP
  - Position and team (as categorical variables)

## Approach

- Split data: Train on seasons before 2010, test on seasons from 2010 onward
- Models used: Logistic Regression, Random Forest, XGBoost
- Oversampling with SMOTE to handle class imbalance
- Limit predictions to 15 All-NBA players per season (to match real-world format)
- Evaluate using precision, recall, F1-score
- Output includes side-by-side comparison of predicted vs actual All-NBA selections per year

## Motivation

I follow the NBA closely and wanted to see what actually drives All-NBA selections. 
This project is a way to test whether stats alone can predict one of the league's highest honors.
It can prove a suspiciton I have that there is more to basketball then analytics, like inagibles that could seperate the best players in the league, at least to an extent. 
It can also prove the biases in the historic voting process, and give analytic proof that its not the best 15 players, but other factors like market, popularity, etc.

## Challenges

- Only a small percentage of players are selected each year, making the classes highly imbalanced
- All-NBA isn’t purely stat-based—factors like team success, market size, and narrative can affect voting
- Stats evolve over time (e.g., 3-point era), so older data may not match modern trends

## Ethics

The model only uses public player performance data. Still, it can reflect historical biases (e.g., favoring certain positions or team records). Predictions shouldn’t be treated as definitive rankings of player value. 
This model could also be misused for potetnial betting purposes, which can also raise ethical concerns. 
