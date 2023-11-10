# Video game project

### Project Overview
A guided project completed through Data Camp; the objective was to explore the top 400 video games created between 1977 and 2020. The task was to compare game sales with critic and user reviews to establish improvement and growth.

### Data Sources
The primary datasets used for this analysis: 'game_sales_data.csv' and 'game_reviews.csv'

### Tools and concepts used
- PostGreSQL
- Selecting columns from a table
- Filtering rows and grouped data
- Using aggregate functions
- Performing calculations on groups of rows
- Left and inner joins
- Union and intercept
- Subqueries

### Interesting code of note
```PostGreSQL:
SELECT g.year, COUNT(g.game) AS num_games, ROUND(AVG(r.user_score),2) AS avg_user_score
FROM game_sales AS g
INNER JOIN reviews AS r
ON g.game = r.game
GROUP BY g.year
HAVING COUNT(g.game) > 4
ORDER BY avg_user_score DESC
LIMIT 10;
```

### Results/findings
The results can be summarized as follows:
1.
2.
3.

### Recommendations/further study
