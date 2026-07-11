# Task 4 — Sentiment Analysis on Social Media Data

## Objective
Analyze and visualize sentiment patterns in social media data to understand public opinion and attitudes towards specific topics or brands.

## Dataset
Twitter Sentiment Analysis Dataset — tweets labeled by sentiment (Positive, Negative, Neutral, Irrelevant) across various brands and topics (gaming titles, tech companies, etc.)

## Approach
- Cleaned tweet text: removed URLs, mentions, hashtags, punctuation, and extra whitespace using regex
- Removed rows with missing tweet text and duplicate entries
- Analyzed overall sentiment distribution across the dataset
- Broke down sentiment by entity/brand to identify topic-specific patterns
- Performed word frequency analysis on positive tweets, filtering out stopwords to surface meaningful terms

## Tools Used
Python, Pandas, Matplotlib, Seaborn, Regex (re), Collections (Counter)

## Key Insight
Sentiment was fairly balanced overall, but varied sharply by brand — MaddenNFL and NBA2K faced strong negative sentiment, while WorldOfCraft was a notable exception with more neutral reception. Positive tweets consistently used clearly positive language ("love," "good," "best"), validating the dataset's sentiment labeling.

## Files
- `task4.ipynb` — full code: cleaning, sentiment analysis, visualizations
- `data/` — Twitter sentiment dataset used