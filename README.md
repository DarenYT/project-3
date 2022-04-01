# README

## Executive Summary 

The pandemic has resulted in a surge in people with mental health problems. As they are less likely to see a therapist in person, increasing numbers of people are turning to online avenues for consolation. As the long reach of the internet makes the world smaller, there comes a point where the demand of online mental health services exceeds any company's ability to manage it effectively, which is what we have machines for.

A key concern for any instituition dealing with mental healthcare is ensuring that the appropriate healthcare is supplied to the correct people when they need it, which is only made all the more difficult when there is an excessively large number of people that all seemingly require urgent care. By training a classifying model to identify high-risk individuals, I hope to be able ease the burden off of mental healthcare companies by allowing them to potentially use the classifier model in conjunction with a chat bot to help prioritising those that need their attention more urgently.

Using submission posts from the r/Depression and r/SuicideWatch subreddits, we were able to train a baseline Multinomial Naive Bayes classifier model with a TF-IDF vectorizer that had an accuracy score of 71.3% and a false omission rate of 28%. We then managed to improve on this with models with accuracy scores of 72.1% and false omission rates of 27.4%. While this does not seem like a large improvement, it is considerable when taking into account the similarity of the classes, and while accuracy is the score that we are always aiming to increase, the false omission rates are also an important metric to keep an eye on.

This is just the beginning, and there is a lot more development that can done on this classifier to improve it. All we need is just time and the right resources!

## Data Dictionary

|Name|Data Type|Description|Size|
|:--:|:--:|:--:|:--:|
|`depression`|pandas.core.frame.DataFrame|Scraped title and selftext submission post data of r/Depression | (10018, 2)|
|`suicidewatch`|pandas.core.frame.DataFrame|Scraped title and selftext submission post data of r/Depression | (10018, 2)|
|`df`|pandas.core.frame.DataFrame|Combined dataframes of `depression` and `suicidewatch`|(9939,3)|
|`stopwords_subr`|list|list of stopwords concering the subreddit titles and individual words they are composed of in order to prevent leaky data|4|
|`stopwords_tifdf`|list|list of stopwords obtained from inputting lists of stopwords with low coefficients into a Multinomial NB TFIDF model until it produced its maximum score|13607|
|`stopword_add`|list|list of stop words from`stopwords.words('english`), `stopwords_tifdf`, and `stopwords_subr`||13790|
|`words_coefs`|pandas.core.frame.DataFrame|Dataframe of words from the corpus and their corresponding predictive coefficients|(24747, 2)|


