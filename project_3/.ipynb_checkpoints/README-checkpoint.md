# Project 3: Web APIs & NLP

---

# Problem Statement

A [study](https://www.straitstimes.com/singapore/health/imh-study-points-to-likely-increase-in-mental-health-issues-in-spore-amid-covid-19) conducted by Institute of Mental Health (IMH) and The University of Hong Kong (HKU) between May 2020 and June 2021 revealed that 13% of the 1,000 local participants reported symptoms of anxiety or depression during the Covid-19 pandemic. Mental health issues, if left neglected, will become more difficult to treat and recover. As such, there is a motivation to identify people who are potentially suffering from mental illness through machine learning in order to encourage them to seek for social support or early medical treatment.

This project aims to investigate if a NLP classifier could identify troubled individuals through their writing (e.g. social media posting). To train and build such NLP classifier model, a large set of training data is required but unfortunately it is not readily available. As a novel approach, text based information from subreddits [r/MentalHealthUK](https://www.reddit.com/r/MentalHealthUK/) and [r/britishproblems](https://www.reddit.com/r/britishproblems/) will be scraped using pushshift API to produce the necessary data to train the NLP classifier model. r/MentalHealthUK provides a pool of relevant text that are related to mental well-being, while r/britishproblems provides a pool of text with negative sentiment. 

If the NLP classifier is proven successful in differentiating the posts between the 2 subreddits, it then be deployed to identifying individuals that are potentially suffering from mental issues from individual that are just complaining or ranting about issues. 

# Modelling

For this project, the models will only be built with the bag-of-words method.Bag-of-words models treat text as a collection of set of words where the frequency of occurrence of each is used as a predictor.


Classification methods selected for this project:
1. Dummy Classifier (baseline)
2. Multinominal Navie Bayes
3. Logistic Regression
4. K-nearest Neighbour 
5. Decision Tree Classifier
6. Random Forest Classifier 

Model will be built to optimise the **recall** performance. In other words, the model is expected to predict lesser false negative but with a trade off of more of false positive. This acceptable as the goal is to identify as many potential mentally ill people as possible so to encourage them to seek for early medical treatment.

# Conclusion

**Summary**:

To recap, there is a growing population of people suffering of mental health related issues. This drive an interest to use machine learning to identify such individuals and encourage them to seek medical treatment as soon as possible. As a novel approach, a NLP classifier is trained using the text data set from subreddit r/MentalHealthUK and r/bristishproblems. It is then envisage that the final machine learning model could identify individual with mentally illness through their social media posting.

For the selected production model (TFIDF, multinomial Navie Bayes), it scored 99.6% on recall and 90.6 accuracy based on unseen data. As such, the numbers indicate a good confidence that the NLP classier is able differentiate posts between the 2 subreddits. This result is encouraging and next step should be investigate with broader set of data for further validation.

**Words association**:

The production model associated the following words (features) with the respective subreddits. LEFT: r/MentalHealthUK, RIGHT: r/bristishproblems
![reddit_wordcloud](./images/reddit_wordcloud.png)

**Improvement**:

1. The reddit posts from r/bristishproblems was scrapped from 11 Jan 2022 to 22 Dec 2021. This could explained the large number of words associated with festive season e.g.Christmas, year etc. To improve model further, the training set should consider seasonality cycle. Hence, sampling from Jan - Dec could be a better approach. 

2. Word sequence method can be used instead of bag-of-word method for machine learning. 

3. The subreddits chosen were created for UK community. As such there might be some linguistic differences and how locals express their ideas and emotion online. 
