Project Proposal
================

## Introduction

The task will be to conduct sentiment analysis on news text within the financial domain. The different classes of sentiment that will be captured are positive, negative, and neutral. This means that our task is a multi-class classification task, where the input is a text/document from twitter and the output is the sentiment (1 is positive, 0 is neutral, and -1 is negative).

## Motivation and Contributions/Originality

Extracting sentiment from financial news texts/articles or social media posts can have great impacts. This is not only because the sentiment can be used to analyze historical events within markets, but also could potentially be used for future speculation and prediction of market behavior. News and public opinion can potentially carry very relevant data for both of analysis and prediction, which makes sentiment analysis of these texts an ideal starting task for future downstream tasks.

Sentiment analysis of news within the financial domain is not a novel idea. Our goal for this project is to explore new methodologies in modeling and hopefully gain new understandings about this task. This means that we will be be reviewing previous studies and then synthesizing those findings with our own ideas into new approaches. A more robust model in predicting sentiment from financial textual data can help achieve both of these.


## Data

We will use tweets and news headlines about publicly traded stocks in
the US stock market from this
[source](https://www.kaggle.com/vivekrathi055/sentiment-analysis-on-financial-tweets)
for the model building. Data were collected from CNBC, Bloomberg,
Twitter, MarketWatch, Bitcoin, etc.

  - Genre: social media and news media
  - Language: English only
  - Language Style: both formal and informal language
  - Size: corpus consists 28440 tweets and news headlines, all of them
    are already annotated for sentiment orientation. We will divide the
    dataset into train, development and test sets for the model
    building. We will save the data in a .csv file.

## Engineering

  - Computing Infrastructure: we will conduct data wrangling, data
    preprocessing, and initial model building on our personal computers,
    run and test deep learning models on Google Colab.
  - DL-NLP method: we will employ Convolutional Neural Network(CNN) for
    Sentiment Analysis. We will probably employ Bidirectional Encoder
    Representations fromTransformers(BERT) to build another sentiment
    analysis model if we have enough time after the first model is
    completed.  
  - Framework: the [Convolutional Neural Network
    tutorial](https://github.ubc.ca/MDS-CL-2019-20/COLX_585_trends_students/blob/master/labs/Lab1/cnn_text.ipynb)
    from week 1 is the codebase we will start off with.

## Previous Works

  - [BERT for Stock Market Sentiment
    Analysis](https://ieeexplore-ieee-org.ezproxy.library.ubc.ca/stamp/stamp.jsp?tp=&arnumber=8995193).
    The purpose and methods used in this article could be referenced by
    us during the model building process.
  - [Measuring News Sentiment](https://www.frbsf.org/economic-research/publications/working-papers/2017/01/). 
    The methodologies and datasets explored in this paper could help us further
    during the model building process and corpus selection.
  - [Predicting Financial Markets: Comparing Survey, News, Twitter and Search Engine Data](https://arxiv.org/abs/1112.1051).
    The analysis of the task and datasets in this paper could be referenced
    when justifying our dataset selection and interpretations of our findings.

## Evaluation

We will use macro F1 score to evaluate the model performance.
