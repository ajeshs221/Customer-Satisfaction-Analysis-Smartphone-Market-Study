# Customer-Satisfaction-Analysis-Smartphone-Market-Study
Customer Satisfaction Analysis: iPhone 17 Pro Max vs. Google Pixel 10 Pro vs. Samsung Galaxy S26 Ultra
📱 Overview

A full-stack data pipeline that scrapes, cleans, and analyzes real-world customer reviews to determine which 2025 flagship smartphone delivers the best customer satisfaction — going beyond simple star-rating averages by combining transformer-based sentiment analysis with statistical bias correction.

🎯 Problem

Star ratings alone don't capture the emotional nuance, sarcasm, or depth of reasoning in written reviews, and comparing products with unequal review volumes (331 vs. 330 vs. 462 reviews) introduces sampling bias. This project builds a rigorous, reproducible methodology to solve both problems.

⚙️ Pipeline
Web Scraping — Collected 1,123 customer reviews from Best Buy using Selenium + undetected-chromedriver, with fallback URL-discovery logic to handle dynamic rendering, pagination, and redirect chains.
Data Cleaning — Regex-based preprocessing (HTML/URL stripping, normalization, noise filtering) to prepare review text for NLP.
Sentiment Analysis — Applied cardiffnlp/twitter-roberta-base-sentiment-latest (RoBERTa) via Hugging Face Transformers to classify each review as Positive/Neutral/Negative with confidence scores.
Composite Scoring — Combined sentiment score (55%) with normalized star rating (45%) into a single 0–100 satisfaction score using Min-Max scaling.
Bootstrap Resampling — Ran 1,000 bootstrap iterations per device to correct for imbalanced sample sizes and generate 95% confidence intervals.
Visualization — Built 5 Power BI dashboards covering review volume, sentiment distribution, rating agreement, and satisfaction score bands.
📊 Key Results
Metric	iPhone 17 Pro Max	Pixel 10 Pro	Galaxy S26 Ultra
Bootstrap Mean Score	94.31	92.85	92.24
% Positive Sentiment	93.96	92.73	91.13
Transformer–Rating Agreement	97.28%	96.97%	95.67%
% Excellent Band (80–100)	93.65%	91.51%	89.61%

The iPhone 17 Pro Max ranked highest across every metric, with statistically significant separation from Samsung (non-overlapping 95% confidence intervals).

🛠️ Tech Stack

Python · Selenium · undetected-chromedriver · Hugging Face Transformers · RoBERTa · Pandas · NumPy · SciPy · scikit-learn · Power BI

