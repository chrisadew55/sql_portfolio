# Video game project

## Table of contents

- [Project overview](#project-overview)
- [Data sources](#data-sources)
- [Tools and concepts used](#tools-and-concepts-used)
- [Interesting code of note](#interesting-code-of-note)
- [Findings](#findings)
- [Ideas for further study](#ideas-for-further-study)
- [Read the Jupyter Notebook!](https://github.com/chrisadew55/video_games_sql/blob/main/video%20game%20project%20notebook.ipynb)
---

### Project overview
A guided project completed through Data Camp; the objective was to explore the top 400 video games created between 1977 and 2020. The task was to compare game sales with critic and user reviews to establish improvement and growth over time, and identify the 'golden age' of video games.

### Data sources
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

### Findings
The results can be summarized as follows:
1. The best selling games were sold between 1985 and 2017
2. The best critically acclaimed games came from the early 90s (1990-95)
3. Based on critic and user reviews in the given dataset, as well as game sales - **2008** is the golden age of video games!

### Ideas for further study
Downloading the full dataset (exceeding 400 games) from [kaggle](https://kaggle.com) to explore the changes in game sales and reviews from 2008 to 2023
