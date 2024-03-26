# NBA Advance Stats Analysis 🏀

**Objective:** Uncover the impact of advanced basketball statistics on NBA team win percentages, utilizing data science techniques to reveal insights into team efficiency and strategy.

---

## 1. Introduction

In the dynamic world of the NBA, the ability to accurately predict team success is invaluable. This project delves into the advanced metrics that potentially influence NBA team win percentages, exploring the statistical underpinnings that drive team performance. By harnessing linear regression, polynomial regression with Lasso, decision trees, and random forests, we aim to shed light on how metrics such as three-point shooting efficiency (`3pt_pct`), rebound rate (`rr`), and true shooting percentage (`ts%`) correlate with winning.

## 2. Data Preprocessing

The analysis begins with a comprehensive dataset extracted from `game.csv`, encompassing a wide range of statistics from NBA games. Here's a breakdown of the initial columns and the advanced metrics derived during preprocessing:

### Initial Columns:
- **`season_year`**: The NBA season year.
- **`team_id_home`**: Unique identifier for the home team.
- **`fga_home`**: Number of field goal attempts by the home team.
- **`fg3a_home`**: Number of three-point field goal attempts by the home team.
- **`fg3m_home`**: Number of three-point field goals made by the home team.
- **`pts_home`**: Total points scored by the home team.
- **`fta_home`**: Number of free throw attempts by the home team.
- **`reb_home`**: Total rebounds secured by the home team.
- **`wl_home`**: Win or loss outcome for the home team.

### Advanced Variables Derived:
- **Rebound Rate (`rr`)**: Calculated as the ratio of total rebounds to the sum of rebounds and rebounds allowed to the opponent. This metric indicates a team's effectiveness in securing rebounds over its opponents.  
rr = reb_home / (reb_home + reb_away)

- **Win Percentage (`win%`)**: Represents the proportion of games won by a team in a season, providing a straightforward measure of overall team success.  
win% = Number of Wins / Total Games

- **True Shooting Percentage (`ts%`)**: A measure of shooting efficiency that considers field goals, 3-point field goals, and free throws.  
ts% = pts / (2 * (fga + 0.44 * fta))

- **Three-Point Attempt Rate (`3pt/fg`)**: The percentage of a team's field goal attempts that are three-pointers, illustrating the team's tendency to shoot from beyond the arc.  
3pt/fg = (fg3a_home / fga_home) * 100


Each of these metrics was meticulously calculated and incorporated into our analysis to provide a multifaceted understanding of team performance indicators. The aim was not only to explore traditional statistics but also to delve into how advanced metrics could influence win percentages, thereby offering insights into modern basketball strategies.

## 3. Exploratory Data Analysis (EDA)

In this section, we delve into the relationships between various basketball statistics and their impact on a team's win percentage. Through visual exploration, we aim to draw meaningful conclusions that could inform team strategies and analytical approaches in basketball.

### Scatter Plot Matrix: `scatter.png`
![Scatter Plot Matrix](plots/scatter.png)
The scatter plot matrix examines the pairwise relationships between our variables of interest and win percentage. Key insights include:
- A positive correlation between `3pt_pct` and `win%` suggests that teams with higher three-point shooting efficiency tend to win more games.
- The `rr` metric shows a substantial positive trend with `win%`, indicating that teams who excel in rebounding are likely to have a better winning record.
- A similar positive trend is observed between `ts%` and `win%`, reinforcing the value of shooting efficiency.
- However, `3pt/fg` presents a less clear relationship, implying that simply attempting more three-pointers does not guarantee higher win rates.

### Coefficient Plot: `Coefficients.png`
![Coefficient Plot](plots/Coefficients.png)
The coefficient plot elucidates the predictive power of each variable within our regression model:
- The `3pt_pct` has a pronounced positive coefficient, asserting its strong predictive power on winning outcomes.
- Rebound rate (`rr`) also displays a substantial positive coefficient, underscoring the critical role of securing rebounds in winning games.
- True shooting percentage (`ts%`) shows a positive impact, albeit to a lesser extent, suggesting its role as a complementary predictor of success.
- Interestingly, the `3pt/fg` coefficient is negligible, which might indicate that it's not the number of attempts but the efficiency of three-point shooting that influences wins.

### OLS Regression Results: `OLS_Regression_Results.png`
![OLS Regression Results](plots/OLS_Regression_Results.png)
The OLS regression results provide a statistical backbone for our analysis:
- The model explains approximately 57.4% of the variance in `win%` (Adjusted R-squared: 0.569), a significant portion, but also indicating room for other factors.
- P-values for `3pt_pct`, `rr`, and `ts%` are well below the 0.05 threshold, confirming their statistically significant impact on the win percentage.
- The large coefficient for `rr` highlights the outsized importance of rebounding on game outcomes in this model.
- The negative coefficient for `3pt/fg` is intriguing, suggesting that a strategy focused solely on increasing three-point attempts may not be as effective as one that prioritizes shooting quality and rebounding.

This exploratory analysis provides valuable insights, but it also emphasizes the complexity of predicting sports outcomes and the need for a nuanced understanding of game dynamics.
