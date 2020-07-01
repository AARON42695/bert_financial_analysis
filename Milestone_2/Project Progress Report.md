Project Progress Report
================

## Introduction

The task will be to conduct sentiment analysis on news text within the financial domain. The different classes of sentiment that will be captured are positive, negative, and neutral. This means that our task is a multi-class classification task, where the input is a text/document from twitter and the output is the sentiment (1 is positive, 0 is neutral, and -1 is negative).

## Motivation and Contributions/Originality

Extracting sentiment from financial news texts/articles or social media posts can have great impacts. This is not only because the sentiment can be used to analyze historical events within markets, but also could potentially be used for future speculation and prediction of market behavior. News and public opinion can potentially carry very relevant data for both of analysis and prediction, which makes sentiment analysis of these texts an ideal starting task for future downstream tasks.

Sentiment analysis of news within the financial domain is not a novel idea. Our goal for this project is to explore new methodologies in modeling and hopefully gain new understandings about this task. This means that we will be be reviewing previous studies and then synthesizing those findings with our own ideas into new approaches. A more robust model in predicting sentiment from financial textual data can help achieve both of these.


## Data

We will use news texts and news headlines from this
[source](https://drive.google.com/file/d/1eqNwkqb1tnaJm_l975K6LJBic8pMof1x/view)
for the model building. Data were collected from CNBC, Bloomberg,
Business Insider, New York Times, Forbes, etc.

  - Genre: news media
  - Language: English only
  - Language Style: both formal and informal language
  - Size: corpus consists  582 financial news texts and news headlines, all of them
    are already annotated for sentiment orientation. Annotations were performed manually by researchers. Minor preprocessing of data should be required in the form of tokenization for models like BERT. We will divide the
    dataset into train, development and test sets for the model
    building. Data is in json format.

## Engineering

  - Computing Infrastructure: we will conduct data wrangling, data
    preprocessing, and initial model building on our personal computers,
    run and test deep learning models on Google Colab.
  - DL-NLP method: we will employ Bidirectional Encoder
    Representations from Transformers(BERT base) to build a sentiment
    analysis model, while comparing the performance between the use of news headlines and news texts from the data. We will probably employ Convolutional Neural Network(CNN) for
    Sentiment Analysis if we have enough time after the first model is
    completed. Transformer models in the Transformers library might be explored as well.
  - Framework: The [BERT tutorial](https://github.ubc.ca/MDS-CL-2019-20/COLX_585_trends_students/blob/master/labs/Lab2/bert_pytorch.ipynb) and the [Convolutional Neural Network
    tutorial](https://github.ubc.ca/MDS-CL-2019-20/COLX_585_trends_students/blob/master/labs/Lab1/cnn_text.ipynb)
    from week 1 is the codebase we will start off with.
  - In week 2 we built a baseline model based mainly on BERT. The model is composed of two parts, a BERT architecture that processes the input sentences and pass along information it extracted from input on to the next model, and a logistic regression model that takes in the output of BERT and classifies each sentence as positive, negative or neutral. The fscore on test result is around 0.63 and accuracy is around 0.73. Since the paper we referenced achieved an fscore of 0.73, we think this model is good enough for us to build on to improve prediction accuracy. Please refer to the model from [here](https://github.ubc.ca/nrubyn/financial_analysis/blob/master/Milestone_2/Initial_Model_Implementation_Bert.ipynb).

## Previous Works

  - [BERT for Stock Market Sentiment
    Analysis](https://ieeexplore-ieee-org.ezproxy.library.ubc.ca/stamp/stamp.jsp?tp=&arnumber=8995193).
    The purpose and methods used in this article could be referenced by
    us during the model building process.
    
    Brief Summary: The authors explored several different models on classifying sentiment of news texts (using the same data set as us). The models attempted were BERT base, Naive Bayes bow, SVM bow, Naive Bayes tfidf, SVM tfidf, and a text CNN. The authors chose to emply BERT base instead of BERT large due to lack of computational resources. All the models performed relatively mediocrely, however the BERT base model performed significantly better than all of the other models. The BERT base model here is pretrained on a massive amount of generalistic text and in this case fine tuned on the financial news data to fit the domain and task better. Additionally, the authors were able to associate historical increases and decreases in the DJI stock market value, concluding, "Therefore, in the analyzed period, 69 % of the periodsbetween opening and closing the stock market, the sentimentof the news was consistent with the stock exchange variation.However, the collection period was short, and more extendedperiods must be evaluated to verify if the observed behaviouris significant." These findings both support our chosen methodology, data set, and motivations for our project. 
    
  - [Measuring News Sentiment](https://www.frbsf.org/economic-research/publications/working-papers/2017/01/). 
    The methodologies and datasets explored in this paper could help us further
    during the model building process and corpus selection.
    
    Brief Summary: The authors explored and developed lexical based sentiminant classifiers, where the data consists of words with associated sentiment scores, rather than example texts. This lexical based computational methodology is proposed by them as an alternative to traditional surverys that government agencies and financial institutes normally use to capture sentiment. The authors utilized a corpus that is quite large actually, consisting of 238,685 news papers from 16 different sources, between 1980 and 2015; within this dataset, 800 news articles were manually annotated for sentiment by research assistants that the authors knew. For lexicons, several different ones were examined and analyzed, leaving the authors to conclude it's best to actually just combine the lexicons altogether and test the different combinations. Additionally, instead of classifying texts as negative, positive, or neutral, the authors use an ordinal classification between 1 and 5 (1 being very negative, 3 being neutral, and 5 being very positive). After determining their best lexical model, the authors compare their performance with off the shelf GloVe and BERT models, where GloVe performed worse but BERT performed similar to their most robust lexical model. The authors argue that lexical models should be preferable in this case because they are easier to interprate for their analysis. The authors also analyized the relevance of their findings, while siting many papers with similar findings, that sentiment of news articles has a relatively high association with consumer and market sentiment. 
    
    
  - [Predicting Financial Markets: Comparing Survey, News, Twitter and Search Engine Data](https://arxiv.org/abs/1112.1051).
    The analysis of the task and datasets in this paper could be referenced
    when justifying our dataset selection and interpretations of our findings.
    
    Brief Summary: The authors here explore several data sets from various sources(Twitter feeds, news headlines, financial data, and Google  search queries) as well as various methods and modeling techniques. However, the purpose of this paper is mainly to analyze and discover whether sentiment analysis is a good tool for predicting market behavior. Additionally, just like the paper above, the authors were seeking to find better alternatives to slow and expensive surveying methods for capturing sentiment. The news data they used was from 8 different sources (Wall Street Journal, Bloomberg, Forbes.com, ReutersBusiness & Finance, BusinessWeek, Financial Times, CNN-Money and CNBC), and scraped news headlines from the sources' twitter pages. For the search engine queries, the authors obtained weekly searchvolume data from Google Insights for specific seed queries (dow jones, stock market, stock to buy, stock , bullish ,bearish , financial news and wall street). For social media data, the authors randomly sample public Twitter posts and categorized them based on the appearance of words within the tweet (i.e. if bullish is in the text, the text is bullish). To track the relevant market state, the authors downloaded daily and weekly DJI average, trading volume, and volitility from Yahoo Finance. Correlation analysis, Granger Causality Analysis, Multiple Regression Analysis, and Forecasting analysis were all used to examine the relationships between temporal market behavior and temporal sentiment. The authors' findings and conclusion implicate that sentiment analysis is still the best discovered, methodology for predicting market behavior, as well as that not just surveys and news articles are good data sources for sentiment analysis. 

## Evaluation

We will use macro F1 score to evaluate the model performance.

## Result

The f1 score for the first trial is around 0.63 from training the headline text.

## Challenges

We were not able to achieve the f1 score from the paper, we will need to do some fine-tuning or use different BERT model. We will try to explore different models for next week. 
