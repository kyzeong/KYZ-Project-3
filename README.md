# SG-DSIF-7 Project 3
# Student's Name: Kong Yin Zeong

### Problem Statement

Mr Najib from MYActive currently has five empty sports hall across Singapore which he wants to turn them into either sport climbing gym or bouldering gym. However, he is not sure which type of sport have more interest in Singapore and he has come to our company for advice. We know that MYActive has a social platform which allows the public to post their idea/comment, we are going to utilize this information and generate a classification model to classify the posts whether they show more interest towards sport climbing or bouldering. 

In order to train our model, we are going to pull the information from Reddit. In Reddit, there are two major subreddits namely Bouldering for people to post anything about bouldering and Climbharder which contains posts mainly for sport climbing.

Performance of the model will be evaluated and the best model will be selected to be implented on MYActive social platform's posts.

---

### Data

The data is collected from two subreddit.

* [`bouldering.csv`](../Data/bouldering.csv): Bouldering Subreddit ([source](https://www.reddit.com/r/bouldering/))
* [`rockclimbing.csv`](../Data/rockclimbing.csv): Climbharder Subreddit ([source](https://www.reddit.com/r/climbharder/))

---

### Summary

5000 posts were collected from each Subreddit namely Bouldering and Climbharder. Each post consists of at least 20 words in the title or the selftext. Distribution of word count was evaluated to identify any relation between title and selftext. After that, title and selftext are combined into a column for further cleaning and processing such as tokenization, stemmatization and lemmatization.

Different classification models were first used to determine the score of each model. The top two models with highest CV score which are SVC and Random Forest were selected for further optimization. In the optimization section, countvectorizer and TFIDF vectorizer were both implemented and different parameters were used to get the most optimized model. After which, Random Forest was selected for further tuning because SVC model is overfitting. 

In the last section we have analyzed the metrics of the Random Forest model such as accuracy, precision, sensitivity, F1 score and et cetera. In order to build a sport climbing gym, it requires more capital so we will reduce Type II error of our classification model. This will ensure the interest in sport climbing is very high when we can classify more than half of the posts.

---

### Conclusion

5000 posts with word count from title or body not less than 20 were collected from ClimbHarder and Bouldering subreddits. Differeny classifer models were used initially in determining which two models can provide better performance and we selected the two models for further optimization. The two models selected were Random Forest Classifier and Support Vector Classifier. After further optimization, we found that Random Forest Classifier is able to provide better result which is not overfitting. 

The performance of Random Forest Classifier has been analyzed with various metrics. In order to set the budget wisely, we have tuned the parameters of the Random Forest Classifier to favor Bouldering which requires less capital in constructin a bouldering gym.

Our client can now implement the final model in their forum to classify the posts whether they are more interest in sport climbing or bouldering.

---

### Recommendation

It takes very long time to run through each model and each parameter, but all models can be further optimized and fine tune if time permits. Due to time constraint, only a few parameters were used in optimization and fine tuning. Besides that, local culture may cause some difference in between the English used by Reddit community and local Singlish. This could be a challenge for our model as it was trained with different sentence structure and phrase used.