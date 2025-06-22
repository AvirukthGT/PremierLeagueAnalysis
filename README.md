# Exploratory Data Analysis of Premier League Player Performance

The goal of this EDA was to uncover meaningful insights into Premier League player performance, team-level efficiency, and tactical patterns using a dataset of player statistics.

## Data Cleaning & Preparation

- Loaded and copied the dataset to preserve the original.
- Handled missing values in `Age`, `BirthYear`, and `Nationality`.
- Converted data types (e.g., `Age` and `BirthYear` to `Int64`) for modeling compatibility.
- Verified data completeness using `.isna().sum()` and `.describe()`.

## Descriptive Statistics & Visual Insights

- Player distributions for goals and assists were highly skewed — median values were near 0 with several outliers.
- Per90 statistics showed wide variance, highlighting highly efficient players with minimal minutes.
- Club-level performance analysis identified top-scoring teams such as Liverpool, Manchester City, and Tottenham.

## Feature Engineering

Created new performance and profile metrics:

- `GoalConversion` = Goals / xG
- `AssistEfficiency` = Assists / xAG
- `AttackingScore` (a weighted performance metric)
- `AggressionIndex` (to profile disciplinary tendencies)

Other engineered features:

- Positional flags
- Finishing tiers based on scoring metrics

## Correlation Analysis

- Strong positive correlations between goals, assists, and expected goal (xG) metrics.
- `MinutesPlayed` was nearly perfectly correlated with other time-dependent stats.
- `GoalConversion` and `AssistEfficiency` were useful for identifying overperformers.

## Club-Level Insights

### Over/Underperformance by xG

- **Overperformers**: Nottingham Forest, Wolves
- **Underperformers**: Crystal Palace, Manchester United

### Efficient Player Identification

- Identified high-impact, underutilized players with high Goals/90 despite low total minutes.

## Tactical Style Clustering

Used KMeans clustering on club-level tactical metrics:

- Progressive passes
- Progressive carries
- xG difference

Identified four tactical profiles:

1. **High progression teams** – e.g., Liverpool, Arsenal  
2. **Low progression & underperformance** – e.g., Ipswich Town, Southampton  
3. **Balanced teams** – e.g., Brighton, West Ham  
4. **Other tactical variations**

## Player Role Archetypes

Applied KMeans clustering to group players into attacking role types:

1. Balanced Attackers  
2. Low Contribution Players  
3. Support Playmakers  
4. High Creativity Specialists  

Visualized clusters on scatterplots using Goals vs. Assists per 90 minutes.

## Reliance Analysis

Calculated reliance on top scorers:

- Brentford and Crystal Palace: 60–70% of goals from top 3 scorers.
- Arsenal and Southampton: More evenly distributed goals across the team.

Created stacked bar charts to visualize top scorer contributions to total team goals.

![image](https://github.com/user-attachments/assets/f50c239f-6394-4bde-a383-e72ac16b9831)

