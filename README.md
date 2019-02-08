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

Moreover some Magazine seems to display on average a more positive tone compared to some other throughout the year of 2018.

![image](https://user-images.githubusercontent.com/42472072/52472291-a1716800-2b9b-11e9-8319-799bbd29de3f.png)

## Latent Drichlet Allocation

Turning to a more advanced statistical analyis we decided to implement a Latent Drichlet Allocation. This is particular uselful in case of categorizing a text in natural language.

The newspaper articles are already sorted by category in our dataset and hence this analysis should be thought much more as an exercise rather than adding structure to the analysis.

The Latent Drichlet Allocation relies on the EM-algorithm to understand the underlying classes in the model. Given a set of classes specified by the user the Latent Drichlet Allocation iteratively optimizes the metaparameters of the model in order to maximize the likelihood that a bunch of words falls into a give class. This iterative improvement takes place through the EM-algorithm.

In the specific case applying the analyis assuming the existence of 5 classes, the most frequent words assigned to each class with the highest probability are shown in the following graph.


![image](https://user-images.githubusercontent.com/42472072/52471895-a97cd800-2b9a-11e9-9480-53a05fa911b6.png)

Interestingly enough the words appearing seems to belong to the same semantic context. The first class seems to very much represent internal politics, the second one seems to refer to macroeconomics and international economics, the third one to internal and external security etc...

Its is moreover possible to check how many words of each magazine falls into one of the different created topics.

![image](https://user-images.githubusercontent.com/42472072/52471512-bea53700-2b99-11e9-9b16-b0a6dfb05631.png)

Here the picture is more scattered but nonetheless some trends are noticeable like the first topic being clearly associated with the Politics Magazine.


## Final Section

The final section contains some refinements to the code displayed so far.

Words are weighted with the **term frequency - inverse document frequency (idf)** statistics that measure how important a word is to a document in a collection (or corpus) of documents.

This have proven to be fundamental in text mining as the importance of the word is now weihted by the numbers of articles in which the word appears. If the word appears in many articles it is possibly a most widly used word that does not relly reveals the context of a text and it is therefore underweighted in comparison to a word that appears frequently in some articles but not so often in general.

According to this new weight new descriptive analysis with the weighted words can be derived and interestingly enought the results quite differ and are more specific. It is less about government in genral but more about Syria and Aleppo etc.

A second improvement is done by looking at bundels of words in the text mining analysis and in the sentiment analysis. Like that we were able to filter out words preceeded by negation terms that would revert the classical meaning of a word and do further refinements, which are outlined in the document.




