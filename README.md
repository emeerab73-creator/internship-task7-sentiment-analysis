# Internship Task 7 – Feedback Sentiment Analysis

## Objective
Evaluate the emotional tone of intern feedback to help improve the internship experience, as part of the Internee.pk Data Analytics Internship (Task 7).

## What was done
- Collected sample intern feedback comments (survey/comment-style text).
- Performed sentiment analysis using Python's **NLTK** library, specifically the **VADER** (Valence Aware Dictionary and sEntiment Reasoner) model — built for short, informal text like reviews and feedback.
- Classified each comment as **Positive**, **Negative**, or **Neutral** based on VADER's compound score, using the standard thresholds (≥0.05 Positive, ≤-0.05 Negative, else Neutral).

## Key finding / limitation discovered
VADER misclassified at least one comment containing "neither...nor" negation (e.g. *"neither impressive nor disappointing"*) as strongly **Negative**, when the sentence was actually neutral in meaning. This happens because VADER scores based on individual word polarity (e.g. "disappointing") without fully resolving negation patterns like "neither...nor." This was verified by testing the phrase in isolation, confirming it's a model limitation rather than a data or code error.

## Results
Out of 20 feedback comments: **12 Positive, 8 Negative, 0 Neutral.**

## Tools used
- Python
- NLTK (VADER SentimentIntensityAnalyzer)
- Pandas
- Google Colab

## Files
- `feedback_sentiment_analysis.csv` — full dataset with compound scores and sentiment labels
