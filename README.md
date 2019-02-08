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

**Main source:** Text Mining in R - https://www.tidytextmining.com/index.html -.

NB: The second project ('Text Mining') analyzes the differences we do not simply take into account the stopwords but we use instead a frequency based approach. The second project also includes bigrams instead of single words.
Latent Drichlet Analysis to Magazine Articles


