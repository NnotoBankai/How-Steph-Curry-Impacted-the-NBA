# How-Steph-Curry-Impacted-the-NBA
Analyzing Stephen Curry’s Impact on the
NBA Through Three-Point Shooting
CIS 4170 - Data Visualization
Nicholas Noto
nicknoto89@gmail.com
1. Introduction
1.1 Project Overview
Stephen Curry has transformed the game of basketball through his exceptional three-point
shooting. This project aims to analyze the evolution of three-point shooting in the NBA,
highlighting Curry’s influence compared to league averages and other legendary shooters.
Using Python for exploratory data analysis (EDA) and Tableau for visualization, this report
examines key trends, statistical comparisons, and predictive models to estimate future
performance.
1.2 Objective
●
●
●
Assess Stephen Curry’s three-point shooting performance over time.
Compare Curry’s statistics with league averages and other elite shooters (e.g., Klay
Thompson, Ray Allen, Reggie Miller, James Harden, Damian Lillard).
Predict Curry’s future three-point shooting efficiency using regression models.
2. Data Acquisition & Preprocessing
2.1 Dataset Overview
The dataset consists of NBA player statistics over multiple seasons, focusing on three-point
shooting metrics. The data sources include:
●
●
Basketball Reference & NBA API: Player-level statistics.
Tableau Dataset: Cleaned, merged player stats dataset.
Key Columns:
●
Player Name, Season, Games Played (GP), Field Goals Made (FGM), Field Goals
Attempted (FGA), Three-Point Made (3PM), Three-Point Attempted (3PA), Three-Point
Percentage (3P%), Effective Field Goal Percentage (eFG%), Points Per Game (PPG),
True Shooting Percentage (TS%).
2.2 Data Cleaning & Transformation
●
●
Missing Values:
○
Minor gaps in three-point percentage (3P%) filled using moving averages.
○
Outlier detection for extreme shooting efficiency values.
Feature Engineering:
○
Created ‘Three-Point Contribution to Total Points’ metric.
○
Computed rolling averages for Curry’s shooting trends.
3. Exploratory Data Analysis & Key Findings
3.1 Three-Point Evolution: Stephen Curry vs. NBA Average
●
Visualization (Tableau): A line graph comparing Curry’s 3P% with the league average.
●
Observations:
○
○
○
Curry consistently outperforms the league average.
A dip in performance in certain years (2019) aligns with injuries.
The league’s 3P% has gradually increased, indicating Curry’s influence.
3.2 Curry’s Three-Point Contribution to Total Points
●
Visualization (Tableau): Three-Point Contribution vs. League Average.
●
Findings:
○
Curry’s scoring is heavily reliant on three-pointers (~50% of total points in some
seasons).
○
League-wide trends suggest an increasing reliance on three-point shooting.
3.3 Misses Needed for Curry to Match Other NBA Greats
●
●
Visualization (Tableau): A horizontal bar chart showing the number of missed
three-pointers Curry would need to match the career 3P% of other top shooters.
Findings:
○
○
Curry maintains a higher efficiency than many elite shooters.
He would need to miss over 27 additional three-pointers to match James
Harden’s efficiency.
○
Curry outperforms Ray Allen and Reggie Miller in career 3P%.
4. Predictive Modeling & Future Trends
4.1 Regression Analysis for Predicting Curry’s Future 3P%
Using Python, multiple regression models were applied to predict Curry’s future 3P%.
4.1.1 Linear Regression Model
●
Model Summary:
○
Input features: Season, 3P Attempts, 3P Makes.
○
Linear trend shows a slight decline in Curry’s efficiency as he ages.
○
Prediction for 2025: ~36% 3P% (dependent on volume and health).
4.1.2 Polynomial Regression Model
●
Model Summary:
○
Captures non-linear fluctuations in Curry’s shooting efficiency.
○
Predicts an initial decline followed by a slight rebound, reflecting possible
adaptation in shot selection.
4.1.3 Observations
●
●
Regression models indicate that while Curry’s efficiency may slightly decline, his ability
to adapt will be crucial in maintaining elite shooting.
Injuries, changes in playstyle, and team dynamics will influence future performance.
5. Conclusion & Key Takeaways
●
●
●
●
Stephen Curry has redefined NBA shooting trends, consistently outperforming league
averages.
The league has adapted to Curry’s style, with an increase in three-point attempts across
teams.
Predictive models suggest a potential decline in Curry’s efficiency, but his historical
adaptability suggests he can sustain high effectiveness through adjustments in shot
selection.
His legacy as the greatest shooter of all time is statistically supported, reinforcing his
transformative impact on the game.
6. Appendix
Appendix A: Python Code for EDA & Regression Analysis
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.linear
_
model import LinearRegression
from sklearn.preprocessing import PolynomialFeatures
# Load data
df = pd.read
_
csv("nba
_
data.csv")
# Plot Curry's 3P Attempts vs. Makes
df
_
curry = df[df['Player'] == 'Stephen Curry']
plt.figure(figsize=(10, 6))
plt.plot(df
_
curry['Season'], df
_
curry['3PA'], label='3P Attempts'
, color='blue')
plt.plot(df
_
curry['Season'], df
_
curry['3PM'], label='3P Makes'
, color='orange')
plt.legend()
plt.title("Stephen Curry's Three-Point Shooting Over Time")
plt.xlabel("Season")
plt.ylabel("Attempts & Makes")
plt.show()
# Linear Regression for 3P% prediction
X = df
_
curry[['Season']]
y = df
_
curry['3P%']
lin
_
reg = LinearRegression()
lin
_
reg.fit(X, y)
y_pred = lin
_
reg.predict(X)
plt.scatter(X, y, color='blue'
, label='Actual 3P%')
plt.plot(X, y_pred, color='orange'
, label='Regression Trend')
plt.title("Stephen Curry's 3P% Prediction")
plt.xlabel("Season")
plt.ylabel("Three-Point Percentage")
plt.legend()
plt.show()
Appendix B: Tableau Visualizations
Screenshots of the Tableau dashboards showcasing:
●
Three-Point Evolution: Curry vs. League Average.
●
Three-Point Contribution to Total Points.
●
Misses Needed for Curry to Match Other NBA Greats.
.
Appendix C: Python Visualizations
Screenshots of Python showcasing:
●
Steph Curry’s Three-Point Shooting Over Time
●
Comparison of Career 3P% Among Nba Greats
Appendix D: Predictive Modeling
Screenshots of the Python Predictive Models:
●
Linear Regression Model
●
Polynomial Regression Model
