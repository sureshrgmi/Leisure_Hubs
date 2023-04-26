# Project Description
This project involves utilizing twitter data to analyze the most frequent leisure hubs locations in London and Brighton in order to recommend suitable locations for the businesses to start their new locations or expand. The project involves the following phases:

### Data Collection
Collecting a large number of geo-tagged tweets from Twitter that are posted in London and Brighton. [Details](Collecting_tweets_from_twitter_API.md)

Once the data is collected from twitter API (which will be a large CSV in GBs), only the relevant records/data should be kept which can be done using following code written in Python. [Link](Reading_Large_CSV.ipynb)

### Data Preprocessing
Preprocessing the collected tweets by removing irrelevent information such as URLs, hashtags and user mentions and only retai  the necessary text and geo-location information.

### Sentiment Analysis
Performing sentiment analysis on the tweets in each location cluster to determine the overall sentiment associated with the location

Following is the link to the code for data preprocessing and sentiment analysis. [Link](Data_Preprocessing_And_Sentiment_Analysis.ipynb)
### Location Clustering
Using spatial clustering algorithms such as K-Means clustering and DBSCAN to group the tweets into different clusters representing potential leisure hubs.

Here is the link to the files 
DBSCAN : [Brighton](DBSCAN-Brighton.ipynb) [London](DBSCAN-London.ipynb)
K-Means: [Brighton](K_Means_Brighton.ipynb)

### Visualization 
Performing the visualization of the data utilizing the spatial, sentiment and temporal features and gathering the information from the data.

### Recommendation
Making recommendations based on the analysis result to the relevant stakeholders such as small businesses, startups, local council and tourism organizations.
