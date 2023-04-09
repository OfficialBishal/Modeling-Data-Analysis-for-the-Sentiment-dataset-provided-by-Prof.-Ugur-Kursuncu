# Modeling & Data Analysis for the "Sentiment" dataset provided by Prof. Ugur Kursuncu
**Assignment:**
* Perform a descriptive statistical analysis of the data and make interesting inferences.
* Create models that predict the probability of each type of sentiment for each tweet.
* Design and explain the data science pipeline followed in this task involving Data preprocessing, Data Analysis, Feature Engineering, Modeling, and Evaluation.

**[Notebook Link]**(https://nbviewer.org/github/OfficialBishal/Modeling-Data-Analysis-for-the-Sentiment-dataset-provided-by-Prof.-Ugur-Kursuncu/blob/main/main.ipynb)

**Professor:** Dr. Ugur Kursuncu

**Author:** Bishal Shrestha

**Date:** 9th April 2023

## Summary of my findings:
> **Finding 1:** The dataset is imbalanced: 48.4% are neutral, 37.2% are positive and 14.5% are negative.  

> **Finding 2:** The "baseline accuracy" of the model for each training, validation (dev set according to the question), and test dataset are approximately 48.4%, 44.7%, and 44.1%, respectively.  

> **Finding 3:** The distribution plot of training dataset lengths (# of characters) shows that 99.9% of the Twitter text has less than 150 characters. Hence, these tweets can be trimmed to 150 characters.

> **Finding 4:** I predicted the language for the tweets using `langdetect` and observed several languages, including 'fr', 'af', etc. However, when I read the tweets, they all appear to be in English. Hence, I did not find predicting language to be an interesting direction to pursue.

> **Finding 5**: Comparing the word frequency distribution of the words in the tweets for the three classes, I find that there are no words that could be used as a marker/sign of a particular class.

> **Finding 6:** There are 5,466 unique words in the entire dataset, which is only a small portion of the English language vocabulary. This suggests that the data can be prone to overfitting issues, and third-party word embeddings can be helpful. It also helps me decide the 'vocabulary size' parameter for the word embedding tasks.

> **Finding 7:** The first model trained, a Bi-LSTM with one-hot encoded vector sequence, achieves an accuracy of 60.1% on the test dataset in 5 epochs. After five epochs, the model starts to overfit.

> **Finding 8:** 'Class weighting', to account for the imbalanced dataset, did not improve the accuracy of the Bi-LSTM model.

> **Finding 9:** Using the 'self-trained word embedding' also did not improve the accuracy of the Bi-LSTM model.

> **Finding 10:** The use of padding in the embedding also did not improve the model's accuracy.

> **Finding 11:** Replacing word embeddings trained locally with `GloVe` embedding increased the accuracy to 65%, **around a 5% increase**. Similar improvement is observed across other metrics (precision, recall, and F1-score).

> **Finding 12:** The second model trained, a transformer network, only achieved an accuracy of 58.3% accuracy. Since transformer networks work well when the dataset is large, I assume that this is 'expected' for our dataset. 
