#News category classifier using nlp models
**Text Classification**

Text classification datasets are used to categorize natural language texts according to content. For example, think classifying news articles by topic, or classifying book reviews based on a positive or negative response. Text classification is also helpful for language detection, organizing customer feedback, and fraud detection.

While this process is time-consuming when done manually, it can be automated with machine learning models.

Category classification, for news, is a multi-label text classification problem. The goal is to assign one or more categories to a news article. A standard technique in multi-label text classification is to use a set of binary classifiers.

**Know about Data**

For the task of news classification with machine learning, I have collected a dataset from Kaggle, which contains news articles including their headlines and categories.

Data Fields

->Article Id – Article id unique given to the record
->Article – Text of the header and article
->Category – Category of the article (tech, business, sport, entertainment, politics)

**Data Cleaning and Data Preprocessing**

 Data preprocessing is the process of transforming raw data into an understandable format. It is also an important step in data mining as we cannot work with raw data. The quality of the data should be checked before applying machine learning or data mining algorithms.
 
 **Split into Train/Test Data and Vectorize the Text with TfidfVectorizer**
 
We need to convert our text into vectors (meaningful representation of numbers) with a vectorizer, as our model can only deal with numbers, not alphabets. First, as with any machine learning task, we split our data into 2 groups of rows, the train and test sets using the train_test_split() function before vectorizing it.

**Fit on Train Data, Transform both Train and Test Data**

The tfidf_vectorizer was uniquely fitted on only our training data to note all the terms involved, we then transform the training data into vectors which account for the frequency of this terms. This is done by the fit_transform() function below (two steps are involved here). We then use the same model to transform the test data into vectors.

**Test the Model with Some Text**

Here comes the fun part. Let’s now test the model with some text! We create a function that takes in the text, vectorize it by using the transform() function of the tfidf_vectorizer that was fitted on our training data earlier, and use the svc_classifier model that was trained earlier to predict the news category and print it out.

