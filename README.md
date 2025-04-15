The goal of this EDA was to uncover meaningful insights into Premier League player performance, team-level efficiency, and tactical patterns, using a dataset of player statistics.

🧼 Data Cleaning & Preparation
Loaded and copied the dataset to preserve the original.

Handled missing values in Age, BirthYear, and Nationality.

Converted data types (e.g., Age and BirthYear to Int64) for modeling compatibility.

Verified data completeness via .isna().sum() and .describe().

📈 Descriptive Statistics & Visual Insights
Players had skewed distributions in goals and assists — median values near 0, with some outliers.

Per90 stats showed wide variance, revealing highly efficient players with low minutes.

Club-wise performance analysis identified top-scoring teams (Liverpool, Man City, Tottenham).

🛠️ Feature Engineering
Created metrics like:

GoalConversion = Goals / xG

AssistEfficiency = Assists / xAG

AttackingScore (weighted performance metric)

AggressionIndex (disciplinary profile)

Generated positional flags and finishing tiers.

🔥 Correlation Analysis
Strong correlations between goals, assists, and xG metrics.

MinutesPlayed had near-perfect correlation with other time-based stats.

GoalConversion and AssistEfficiency helped identify overperformers.

📊 Club-Level Insights
Over/Underperformance by xG:

Nottingham Forest & Wolves overperformed xG.

Crystal Palace & Manchester United underperformed.

Efficient Players:

Identified underutilized high-impact players with high Goals/90 and low total minutes.

🧠 Tactical Style Clustering
Used KMeans to cluster clubs based on:

Progressive passes

Progressive carries

xG difference

Identified 4 tactical profiles:

High progression (Liverpool, Arsenal)

Low progression & underperformance (Ipswich Town, Southampton)

Balanced teams (Brighton, West Ham)

👥 Player Role Archetypes
Clustered players into 4 attacking role types using KMeans:

Balanced Attackers

Low Contribution Players

Support Playmakers

High Creativity Specialists

Visualized these roles on scatterplots of Goals vs Assists per 90 mins.

⚽ Reliance Analysis
Calculated how much clubs depend on top 1 and top 3 scorers.

Brentford and Crystal Palace relied on 60–70% of goals from top 3 players.

Arsenal and Southampton had more balanced goal distribution.

Visualized stacked bars of top scorers’ contribution to team goals.

