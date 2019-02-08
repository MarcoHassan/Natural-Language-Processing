# R Natural Language Processing

### Authors: Antoine Gex-Fabry, Marco Hassan, Jonas Clemens

### Three days project on text mining, sentiment analysis and a final Latent Drichlet Allocation.

# Goal of the project
This part is a baseline model to do Topic Modelling. In this project, the goal is to fit an LDA model to the news articles and analyze and interpret the results intuitively. Here are the main elements of the analysis:

Corpus: Newspaper articles from Reuters. (Source: Kaggle )
Document: Single articles from the Corpus.
Topic: To be determined by the models. Note: there are five pre-determined categories in the database Inlandsnachrichten, Politik, Weltnachrichten, Top-Nachrichten, Breakingviews).
First to preprocess the data by cleaning it. Once the data is cleaned (see first section for the details of the cleaning implementation), some descriptive statistics are offered. In particular, the number of distinct words and the most frequent words appearing overall and by category.

In the subsequent section, we use publicly available lexicons to attribute "sentiments" to the words of our Corpus. We then analyse the amount of positive and negative sentiments in the Corpus.

Finally, we fit an LDA model and analyze what every Topic contains.

**Main source:**  <a href = "https://www.tidytextmining.com/index.html" target = "_blank">Text Mining in R</a>

NB: The second project ('Text Mining') analyzes the differences we do not simply take into account the stopwords but we use instead a frequency based approach. The second project also includes bigrams instead of single words.
Latent Drichlet Analysis to Magazine Articles

## Data Cleaning

First we have to clean and preprocess the data. The following steps are made to do so:

- Keep only the articles with at least approx. 250 words (arbitrary number).
- Select a random sample of size 1'000.
- Remove all the punctuations, the possessive forms ('s), the word 'reuter'.

Then we do preliminary cleaning. In particular, keeping only the articles with at least 250 words (arbitrary number, approximation). Then we randomly select a subsample of size $N$.

## Descriptive Statistics

This are genearal descriptive statistics for the whole Corpus.

![image](https://user-images.githubusercontent.com/42472072/52470610-56555600-2b97-11e9-9eb5-0f7f81ecbe05.png)

![image](https://user-images.githubusercontent.com/42472072/52470917-2490bf00-2b98-11e9-9404-0729c3082e0d.png)

## Sentiment Analysis

We subsequently analyzed the sentiment in the Corpus through two dictionaries. We just kept words falling in the categories "positive" and "negative" in the dictionaries.

Note that changing the lexicon has a huge impact on the results. Indeed, "Trump" is not recognised in "nrc", but it's a very frequent word overall. Therefore, it changes the rest of the analysis. 

![image](https://user-images.githubusercontent.com/42472072/52470979-4ab65f00-2b98-11e9-93da-461fc3616868.png)

Based on this analysis we could subsequently identified the atricles scoring worst in the sentiment index and we could quickly read their abstract to get an idea without having to go through all of the huge amount of articles but getting right to the source of the (potential) probelm. 

Interestingly we also decided to plot the most important words in determining the sentiments analysis observing an asymmetric distribution with few positive words appearing more frequently and highly impacting the tone of the newspaper articles.

![image](https://user-images.githubusercontent.com/42472072/52471300-3cb50e00-2b99-11e9-9845-58920e3a0d60.png)






