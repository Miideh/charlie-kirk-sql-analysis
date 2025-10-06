
# Charlie Kirk Twitter SQL Analysis

## Overview
This project analyzes the **Charlie Kirk Twitter dataset** using **Python (Pandas)** and **SQL (SQLite)** within **Google Colab**.  
It demonstrates how SQL-style querying can be applied to real-world social media data for pattern discovery and engagement analysis.

---

## Dataset Information
- **Source:** [Kaggle – Charlie Kirk Twitter Dataset](https://www.kaggle.com/datasets/bwandowando/charlie-kirk-twitter-dataset)
- **Description:** Contains tweets from Charlie Kirk, including metadata such as likes, retweets, quotes, replies, and timestamps.
- **Goal:** Identify engagement trends, assess the influence of keywords, and determine optimal posting patterns.

---

## Objectives
1. Apply **SQL queries** for data summarization, filtering, and aggregation.
2. Perform **data analysis** using Pandas and SQLite in a reproducible environment.
3. Visualize engagement metrics such as likes, retweets, and posting times.
4. Practice **version control** with Git and GitHub.
5. Integrate a **Linear Algebra** component through **Principal Component Analysis (PCA)**.

---

## Tools and Libraries
- Python  
- Pandas  
- SQLite3  
- Matplotlib  
- Seaborn  
- Scikit-learn (for PCA)  
- Google Colab  
- Git and GitHub  

---

## SQL Analysis Summary

| Analysis Type | Description |
|----------------|--------------|
| Dataset Overview | Total tweets, average likes, and retweets |
| Top Performing Tweets | Identify tweets with the highest likes and retweets |
| Monthly Trends | Average engagement per month |
| Hourly Trends | Best posting hours based on engagement |
| Retweet-to-Like Ratio | Engagement efficiency comparison |
| Tweet Length | Relationship between tweet length and performance |

---

## Example SQL Queries

```sql
-- 1. Overview of engagement
SELECT COUNT(*) AS total_tweets,
       AVG(likeCount) AS avg_likes,
       AVG(retweetCount) AS avg_retweets
FROM tweets;

-- 2. Top 10 most liked tweets
SELECT text, likeCount, retweetCount
FROM tweets
ORDER BY likeCount DESC
LIMIT 10;

-- 3. Average likes by posting hour
SELECT strftime('%H', createdAt) AS hour,
       ROUND(AVG(likeCount), 2) AS avg_likes
FROM tweets
GROUP BY hour
ORDER BY hour;
````

---

## Data Visualization

The following visualizations were generated from the SQL and Pandas queries:

1. **Average Likes Over Time** – Monthly engagement trend.
2. **Engagement by Hour of Day** – Identification of peak posting times.
3. **Likes vs Retweets** – Correlation between audience engagement metrics.
4. **Word Count vs Likes** – Influence of tweet length on interaction rates.
5. **PCA Scatterplot** – Engagement clustering based on dimensionality reduction.

---

## Results and Insights

| Category       | Finding                                                                     | Interpretation                                                                                    |
| -------------- | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Posting Time   | Engagement peaks between 7:00 PM – 10:00 PM                                 | Evening hours yield higher visibility and reactions.                                              |
| Keyword Effect | Tweets containing “America” or “Trump” show significantly higher engagement | Emotionally or politically charged terms attract attention.                                       |
| Correlation    | Likes and retweets have a correlation of approximately 0.81                 | Strong linear relationship between these metrics.                                                 |
| Tweet Length   | Tweets between 20–40 words perform best                                     | Concise tweets balance information and readability.                                               |
| PCA            | First component explains 66% of variance, second 17%                        | Majority of engagement variation can be explained by one key factor: audience response intensity. |

---

## PCA Integration

The **Principal Component Analysis (PCA)** was performed on engagement metrics (likes, retweets, replies, quotes, and views).
Findings indicate that the majority of variance is explained by engagement strength, forming clusters between high and low-performing tweets.

---

## How to Reproduce

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/charlie-kirk-sql-analysis.git
   cd charlie-kirk-sql-analysis
   ```

2. **Download the dataset** from Kaggle and upload it to your Colab environment.

3. **Unzip and run the notebook:**

   ```bash
   !unzip charlie-kirk-twitter-dataset.zip
   ```

4. **Open and execute the notebook:**
   `charlie_kirk_sql_analysis.ipynb`

---

## Conclusion

This analysis highlights the relationship between timing, content, and engagement in political Twitter activity.
The study demonstrates how **SQL querying and data visualization** can uncover key behavioral insights from social media datasets.

Key takeaways include:

* Posting time significantly affects engagement.
* Political keywords influence audience interaction.
* Tweet conciseness enhances performance.
* PCA effectively summarizes engagement variance.

