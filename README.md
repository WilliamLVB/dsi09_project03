# dsi09_project03

## Problem Statements
In this era, we are flooded with information. To avoid it, a tool is required to classified information that we can prioritize which information we want to read / absorb.

## Objectives
The objective of this project is to develop a model that can categorize information accurately.

## Methodology
We will use data from Reddit, namely the post in sub-Reddit askscience (https://www.reddit.com/r/askscience/hot/) & science (https://www.reddit.com/r/science/hot/). 
We extract the data with webscrapper from Reddit API. Once data collected, we'll applied Natural Language Processing & classification algorithms (Naive Bayes & Logistic Regression to classify the post.

## Constraints
We selected two similar sub-Reddits to increase the difficulty level. We believe that if our model can accurately classify post from similar sub-Reddits, the model can be developed further to incorporate different sub-Reddits & perform well.

## Data / Materials
Data extracted from Reddit API is stored as "csv" file inside "data" folder.

## Result Summary
|Model|data|accuracy|miss_class|sensitivity|specificity|precision|note|
|---|---|---|---|---|---|---|---|
|Multinomial Naïve Bayes|test|0.856|0.1439|0.8365|0.8693|0.8131|score on test data|
|Log-reg; Bag of Words - stop_word|test|0.8988|0.1012|0.7981|0.9673|0.9432|score on test data|
|Log-reg; Bag of Words - ngram (range: 1-2)|test|0.9339|0.0661|0.9038|0.9542|0.9307|score on test data|
|Log-reg; Bag of Words - stop-word & ngram (range: 1-2)|test|0.8677|0.1323|0.7019|0.9804|0.9605|score on test data|
|Hashing - stop-word & ngram (range: 1-2), all features|all|0.9572|0.0428|0.8984|0.9971|0.9952|score on all data - no train-test split|
|Hashing - stop-word & ngram (range: 1-2), 65k features|all|0.9589|0.041|0.9042|0.9961|0.9936|score on all data - no train-test split|
|Hashing - stop-word & ngram (range: 1-2), 10k features|all|0.9402|0.0598|0.865|0.9912|0.9851|score on all data - no train-test split|
|Hashing - stop-word & ngram (range: 1-2), 5k features|all|0.9291|0.0709|0.8374|0.9912|0.9846|score on all data - no train-test split|
|Hashing - stop-word & ngram (range: 1-2), 1k features|all|0.8699|0.13|0.7315|0.9637|0.9316|score on all data - no train-test split|
|Hashing - stop-word & ngram (range: 1-2), 6615 features|all|0.9414|0.0586|0.8679|0.9912|0.9852|score on all data - no train-test split|
|Log-reg; TFIDF - stop-word, 6615 features|all|0.9607|0.0392|0.9057|0.998|0.9968|score on all data - no train-test split|

## Conclusion & Recommendations / What's Next?
* Get more data - more training for model - better accuracy.
* Play around with model parameters (stop-words - adding new ones, try more ngram,..).
* Excluding common words.
* Analyze miss-classified post.
