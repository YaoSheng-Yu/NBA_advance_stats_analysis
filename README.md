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
