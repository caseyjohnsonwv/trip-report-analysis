# trip-report-analysis
This is mostly a project for me to play with classification models.


## Contents

1. Scrape r/rollercoasters for "trip report" posts
2. Use `gpt-4o-mini` to enrich the raw text with new features
3. Analyze dataset covariance and remove redundant features
4. Train a classification model that can predict, A: "Was the money worth spending?", and B: "Was this a positive experience?"


## Feature Lift Analysis

After training a Random Forest classifier on 183 LLM-enriched trip report posts:

| Feature | Value Sentiment | Experience Sentiment |
| --- | --- | --- |
| Ride Sentiment | 21.7% | 33.8% |
| **Post Month** | **19.4%** | **20.2%** |
| Food Sentiment | 16.1% | 9.8% |
| Crowd Sentiment | 11.2% | 13.3% |

I tried XGBoost as well - it gave much more favor to ride sentiment, but the overall accuracy of the model didn't improve substantially (hovering around 70-80% for both). I have a couple hypotheses to explore about this result, but I don't doubt it.


## Quickstart

Required credentials (see `.env.example`):
- Reddit for Developers client_id & client_secret
- OpenAI API key

```
poetry install
poetry run python -m jupyter notebook
```

## Contact

[DM me on LinkedIn](https://linkedin.com/in/caseyjohnsonwv). My notifications are turned off, but I'll see it fairly quickly.
