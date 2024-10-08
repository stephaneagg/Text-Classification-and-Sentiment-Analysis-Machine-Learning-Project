# Text-Classification-and-Sentiment-Analysis-Machine-Learning-Project
Project used to learn how to use Support Vector Machines and Sentiment Analysis to classify data entries.

The dataset used for this project contains speeches from the UN General debates (1970 - 2017).

Database credit goes to https://github.com/blueprints-for-text-analytics-python/blueprints-text/tree/master/data/un-general-debates
__________________________________________________________________________________________________________________

## Text Classification
Using scikit-learn and NLTK I built a text processing and classifier pipeline to predict the country of a speech. In the interest of runtime, I filtered the database to include only speeches that occured from the year 2000 2017. I createed a pipeline that first transforms the text data into TF-IDF vectors (term frequency–inverse document frequency, a measure of importance of a word to a document in a collection), then applies SVM (Support Vector Machine) to analyze data for classification while referencing a set of stop words to eliminate words that are widely used and carry very useful information for the purposes of this project.



## Sentiment Analysis
