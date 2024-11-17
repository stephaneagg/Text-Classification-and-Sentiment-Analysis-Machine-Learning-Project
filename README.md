# Text-Classification-and-Sentiment-Analysis-Machine-Learning-Project
Machine learning project used to learn how to use Support Vector Machines and Sentiment Analysis to classify data entries.

The dataset used for this project contains speeches from the UN General debates (1970 - 2017).

Database credit goes to https://github.com/blueprints-for-text-analytics-python/blueprints-text/tree/master/data/un-general-debates
__________________________________________________________________________________________________________________

## Text Classification
Using scikit-learn and NLTK I built a text processing and classifier pipeline to predict the country (USA or Canada) of a speech. I first filtered the dataframe to include only entries where country is USA or Canada. I then created a pipeline that first transforms the text data into TF-IDF vectors (term frequency – inverse document frequency, a measure of importance of a word to a document in a collection adjusted for the fact that some words appear more frequently in general), then applies SVM (Support Vector Machine) to analyze data for classification while referencing a set of stop words to eliminate words that are widely used and carry very useful information for the purposes of this project.

The follwoing is the classification report generated by the model. 

<img width="427" alt="Screen Shot 2024-10-09 at 11 32 05 AM" src="https://github.com/user-attachments/assets/7f15ddc8-b7b0-4430-9f97-dc04563f0e01">


The rows of the classification report represent the classes (countries) being predicted.

Each row shows the following metrics
- Precision: The ratio of correctly predicted positive observations to the total predicted positives.
- Recall: The ratio of correctly predicted positive observations to all observations in the actual class.
- F1-score: The harmonic mean of precision and recall. It provides a balance between the two metrics.
- Support: The number of actual occurrences of each class in the dataset.

Given the overall statistics, the model performs well with an accuracy of 89%

The high precision but lower recall for Canadian speeches suggests that while the model rarely incorrectly labels something as Canadian (high precision), it sometimes misses actual Canadian speeches, labeling them as USA instead.

The model has perfect recall for USA speeches, meaning it captures all USA instances accurately. However, the precision for USA is slightly lower, indicating that some Canadian speeches were incorrectly classified as USA.


## Sentiment Analysis

For sentiment analysis I used the Python library TextBlob to analyze the speeches and assign a sentiment score. TextBlob sets the sentiment score as a floating point within the range [-1.0, 1.0], where -1.0 denotes a very negative sentiment, 1.0 denotes a very positive sentiment, and values around 0 denote a neutral sentiment. I then  added a new column to the dataframe containing the sentiment score for the corresponding speech.

The following is a snapshot of the dataframe.

<img width="1015" alt="Screen Shot 2024-10-09 at 12 09 07 PM" src="https://github.com/user-attachments/assets/ae8cedd9-0a1f-422f-b0d9-afea0ebcb4ba">


The average sentiment of each speech for both USA and Canada.

<img width="277" alt="Screen Shot 2024-10-09 at 12 09 35 PM" src="https://github.com/user-attachments/assets/c76788dc-4d2e-4c72-8229-101aa5343df7">


The average sentiment for each speaker

<img width="259" alt="Screen Shot 2024-10-09 at 12 09 46 PM" src="https://github.com/user-attachments/assets/4dd45688-328f-418a-b400-035514c7771c">


The average sentiment for each year sorted in descending order based on their average sentiment.

<img width="625" alt="Screen Shot 2024-10-09 at 12 10 00 PM" src="https://github.com/user-attachments/assets/83e7a2fb-6116-4d71-81b5-c6819c090628">


### List of references used to complete the project
https://scikit-learn.org/stable/modules/svm.html

https://www.geeksforgeeks.org/understanding-tf-idf-term-frequency-inverse-document-frequency/

https://www.nltk.org/

https://textblob.readthedocs.io/en/dev/
