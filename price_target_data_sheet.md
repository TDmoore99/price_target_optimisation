# Datasheet Template

## Motivation

- **For what purpose was the dataset created?**  
  The dataset was created to analyze and predict stock price movements using historical price data and sentiment analysis.
  It is written as a study to see if a Bayesian Optimised Machine Learning Model can get within 20% of analyst predictions.

- **Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)? Who funded the creation of the dataset?**  
  The dataset comes from publicly available financial sources (NASDAQ, Web Searches etc).
  Data for stock prices and news sources is generally available in the public domain, however I have been careful to only use sources where there is no copyright infringement.

## Composition

- **What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)?**  
  The instances represent historical stock prices, including fields such as `close_price`, `date`, `symbol`,
  The sentiment scores derived from news articles within the notebook itself using NLTK sentiment.

- **How many instances of each type are there?**  
  The prices contain several thousand records, with each representing a unique combination of a stock symbol and price for a given day.
  The news articles are a very small subset of data given the amount of news available and there are only a several hundered spanning each stock across several years.

- **Is there any missing data?**  
  Not for the purposes of this notebook, however for a more indepth model you may wish to add more news article data that can adjust and improve of sentiment scores.

- **Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by doctor–patient confidentiality, data that includes the content of individuals’ non-public communications)?**  
  No, the dataset is based on publicly available stock prices and sentiment data. However, care should be taken when using proprietary sentiment data sources.

## Collection process

- **How was the data acquired?**  
  The stock price data was  acquired through public financial data sources such as NASDAQ and Yahoo Finance.
  The sentiment data was be created from news articles collected through web scraping and yahoo APIs news articles and social media posts.

- **If the data is a sample of a larger subset, what was the sampling strategy?**  
  Only the stocks AAPL, AMZN, GOOG and META are included in this analysis.

- **Over what time frame was the data collected?**  
  Data was collected from historical datasets on 12th Sepetmeber 2024. Data spans from December 2018 to September 2024

## Preprocessing/cleaning/labelling

- **Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)?**  
  Data is cleaned in the notebook itself. data cleaning in the notebook comprises of.
    
  - Merging price data with sentiment data based on symbol and date.
  - Filling missing sentiment scores with zeros.
  - Creating new features such as rolling averages for sentiment.

- **Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)?**  
  Raw data is saved in the ./data directory in the github repository. https://github.com/TDmoore99/price_target_optimisation

## Uses

- **What other tasks could the dataset be used for?**  
  The dataset could be used for tasks such as:
  - Stock price forecasting using different machine learning models.
  - Sentiment impact analysis on financial markets.
  - Time series analysis of market volatility.

- **Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses?**  
  The sentiment analysis component could introduce biases based on the sources of the data. Analysts should be cautious of biases in the media coverage that might skew sentiment analysis results.

- **Are there tasks for which the dataset should not be used?**  
  The dataset should not be used for any commercial use. For commercial use I would suggest using market data providers and obtaining news feeds from repoutable news agencies.

## Distribution

- **How has the dataset already been distributed?**  
  If the dataset is publicly available, it could be distributed via public financial data repositories or APIs like Yahoo Finance. 

- **Is it subject to any copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)?**  
  Financial data is often subject to the terms of use from the original provider (In this case the exchange is NASDAQ), and news articles collected from third-party sources could also be protected by copyright or require licensing.

## Maintenance

- **Who maintains the dataset?**  
  Maintenance could depend on the source of the data. Publicly available financial datasets might be maintained by financial data providers, while news articles may be maintained by whomever produced the articles.
