# Project Overview

This project involved the cleaning, transformation, and statistical analysis of a social media sentiment dataset. The primary objective was to take raw, disparate emotional labels and temporal data and convert them into a standardised format suitable for sentiment analysis and engagement pattern research.

## Situation

The original source material, `Sentiments.csv`, consisted of **732 recorded interactions**. The data was unstructured, containing over 200 unique sentiment labels (e.g., "Happy", "Fuming", "Bitterness") and combined "Timestamp" strings that were not suitable for granular temporal analysis. Furthermore, engagement metrics (Likes and Retweets) were separate, making it difficult to assess total reach across different emotional tones.

## Task

The goal was to:

1. **Standardise** the 200+ sentiments into three distinct categories: Positive (1), Neutral (0), and Negative (-1).
2. **Extract** date and time components into separate columns for analysis.
3. **Calculate** total interaction metrics (Likes + Retweets).
4. **Perform regression analysis** to determine if the time of day or sentiment type significantly predicts engagement levels.

## Action

I performed several data transformations using Excel-based logic:

- **Temporal Extraction**: Used the formula `=INT(A2)` for dates and `=MOD(A2,1)` for time components.
- **Sentiment Standardisation**: Collaborated with AI to categorise emotions based on valence. For instance, "Arousal" was reclassified from Neutral to Positive to reflect the context of "positive anticipation". A keyword-matching formula using `SEARCH` and wildcards was implemented to automate this reclassification across the dataset.
- **Engagement Aggregation**: Created an "Interactions" column by summing Likes and Retweets.
- **Statistical Calculation**: Generated R² (coefficient of determination) values to examine the relationships between time, sentiment, and engagement.

## Result

The transformation resulted in a clean, multi-dimensional dataset and a visual dashboard:

- **Sentiment Distribution**: The final count identified **433 Positive, 177 Negative, and 122 Neutral** posts.
- **Platform Engagement**: Total interactions across all platforms reached **47,148**, with Instagram seeing the highest engagement (**17,464**) compared to Twitter (**15,168**) and Facebook (**14,516**).
- **Statistical Insights**: The R² analysis revealed that sentiment is a poor predictor of interactions (**R² = 0.0878**) and that the time of day has almost no correlation with sentiment (**R² = 0.000085**). This suggests that engagement in this dataset is driven by factors other than just emotional tone or timing.

## 📊  Interact with the dashboard

*   **[Download the file from here](Sentiments.xlsx)**

  
## Limitations

Users of this database should be aware of the following constraints:

- **Collection Methodology**: The data was provided as class material by an instructor; however, the original method of collection (e.g., specific API scraping parameters or keyword filters) remains unknown.
- **Ambiguous Metric Labeling**: The dataset uses "Likes" and "Retweets" as universal interaction metrics across all platforms. This is technically inconsistent because "Retweets" is a term exclusive to Twitter; for Facebook or Instagram entries, it is unclear if this represents a "Share," a "Repost," or another form of amplification.
- **Platform-Specific Isolation**: While each entry is assigned to a single platform—such as a Facebook post about a new recipe with 37 total interactions—there is no data indicating if that same content was cross-posted or reshared on other networks. This means the "Interactions" column may only capture a fragment of a post's true global reach.
- **Non-Uniform Engagement Data**: The engagement is not distributed evenly across platforms or regions. In many instances, a country's sentiment data is derived from only one platform, which prevents us from determining if engagement patterns are a result of the content itself or the specific user behaviour of that platform's demographic in that country.
- **Incomplete Interaction Context**: The database identifies 732 recorded interactions but fails to specify the nature of the likes. For example, we cannot distinguish between an Instagram "heart" and a Facebook "reaction" (such as 'Love' or 'Wow'), which carry different emotional weights and algorithmic values.
- **Unknown Collection Parameters**: Because the original scraping or collection method is unknown, we cannot verify if the data was filtered for specific keywords or if it represents an organic, unbiased stream of social media activity. This makes it more accurate to view the dataset as a curated snapshot rather than a comprehensive representation of social media behaviour.
