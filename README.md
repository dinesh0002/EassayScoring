# EassayScoring

## Project Description: 
Automated Essay Evaluation using Machine learning for a better and fast evaluation of essay text for an supervised grading system.

## Code and Resources Used:
Python Version : 3.7.10
Packages: pandas, numpy, sklearn, tensorflow, keras, matplotlib, nltk, re, gensim

## Approach

### Data Cleaning
In the dataset that been provided there are some optional columns that can be removed such as ‘unnamed 0’ and ‘uniqueId’ which provide no useful information for prediction the final test dataset and same process is done to the test set for having same ndarray size while predicting the values.

### EDA for the Dataset
Looked at the various values in the promptId as well as the frequency of  share of various sets in essay with the grades given by the evaluator with the share in percentages 

### Data Feature Selection
features for our dataset which are stopwords, essay length, prompt Id Questions, Sentence Count, Long word Count.

## Data Preprocessing
- Initially in the both dataset test and train, removed the stop words which do not change the sentence meaning from the ‘essay’ column which provides better evaluation.
- Later we use punkt from nltk which tokenizes the text into sentences which can be further used for vectorization 
- Used a function called sent2word which converts the sentences into the individual words and preprocesses with all unnecessary starting letters such as (‘, ”, @, !) and only the words are starting with letters specified from regex (re) 
- Used a function called essay2words which tokenizes all the individual words 
- We convert the training_statements into vectorized form for converting it into numerical values where deep learning can understand and we can fit the values into the model.

## Model Selection and Building
For this case I have used an LSTM which is an artificial RNN which is well studied for classification, processing and making predictions. 
Used Keras for model building and training of the model. Batch size = 64 with 100 epochs 

## Predicting
Predicted the values for the test dataset and concat to one dataframe to to exported as test_prediction.csv

## Improvements:
- Could have made a feature selection such as frequency of Grammar (such as Noun, Adverb, verb,....) in the essay sentences which evaluates the quality of the written work.
- Could have made a feature selection for spelling correction in the essay which adds to the quality writing.
- Could have been more diverse evaluation with more than one evaluator for training data.
- May be I have an High bias in the training phase which can be improved by multi model evaluation with much more relationship between the different categorical variables with the output variable
- While evaluating with internal test_train_split found after the training phase the kappa score for the model which is 0.1678 which could had mismatch with the rounding off the y_test variable which resulted in low kappa score for evaluation 

## Conclusion
Thus, the project of automatic essay evaluation using machine learning is done with various cleaning and preprocessing of the data for making the final predictions using the LSTM model. Going forward I believe that this will be very useful for automating things making simpler for evaluators
