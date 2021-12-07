# Predicting User Retention based on subreddit visits

##  Abstract
User retention is a very import statistic used in a variety of different applications.
Users are very important especially to large corporations such as Google, and Amazon.
Often times we can classify different users into different behaviour groups and look
at how each group affects user retention. Analyzing user's behaviour is very important
task used in the data science industry, so today we will take a look and explore
different user's behaviour from our dataset. Some goals for this project is to
dive into different behavioural data and see if we can find any patterns, this includes
data such as time of day, subreddits similar users, subreddit
topics, and subreddit popularity. I want to provide visualizations for these results 
as well an ensemble of supervised learning models to predict user retentions 
from these behavioral patterns.

## Research Questions

We are interested user retention based on a user's behaviour, here are some questions
we are trying to answer.

1. How can we best predict user retention?

2. Do user retention rates correlate with types of the subreddits they visit?

3. Do user retention rates correlate with the time of day they post?

4. Can we predict user retention from their post past post frequency?

## Proposed Dataset

Regarding extracting subreddit by popularity, I can do this by scraping reddit
and using the number of subscribers as how popular that subreddit is. This is feasible
because there are 100 subreddits in the current dataset. Scraping this can be done with
beautiful soup, where I can get the raw html, and from there grab the subscriber counts.

## Methods

#### User Retention
We define user retention as how long the user stays on the platform. This is time gap
between there first activity and last activity. Frequency is lost during this process.

#### Subreddit Embedding
To better understand our data it is important to visualize our data. Here we define
how close 2 subreddits are by the users they share. Consider matrix n x d matrix where
n is the number of users and d is number of subreddits. matrix[i][j] = 1 if user i
is subscribed to subreddit j. This is very high dimensional space and sparse, so we
use will matrix factorization to push the dimensions back to 2, 
while preserving closeness. Inspired by this [document](https://developers.google.com/machine-learning/recommendation/collaborative/matrix)

#### Supervised Learning
The model I plan to use is a logistic regression model. My training data will be for each user
the subreddits they are subscribed to, as a row in the subreddit embedding matrix, and its label
is how long the user stayed on the platform.

#### Additional Methods
I plan to eventually look at how posting time, subreddit popularity, subreddit topic,
affect user retention too, however for now I will focus on user sharing.
 
