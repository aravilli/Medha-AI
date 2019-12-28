# Objectives for this week :

1) Try some python code to read data ( CSV data ) from a file using Numpy and print first 100 rows, last 100 rows etc 
    refer :  https://www.dataquest.io/blog/numpy-tutorial-python/ 

2) Supervised Learning

Learn Classification Algorithm  (Support Vector Machines ) and try the Digits data Set (for image recognition) using 
sci-kit learn. 

  refer : https://scikit-learn.org/stable/tutorial/basic/tutorial.html

3)  Predicting  Phishing Websites (URLs)

    Data set - Phishing Websites Data Set 
    
    Go through the publicly available dataset from UCI repository.  Phishing Websites dataset consists of 2456 instance 
    with 30 attributes(features) and classification whether the instance is a legitimate one or phishing one. 

    https://archive.ics.uci.edu/ml/datasets/Phishing+Websites 
    
    Download the word document (Phishing Websites Features.docs) which explains about each feature ( IP Address, 
    Long URL, short URL, sub domain name, etc ... ) and understand the data set in detail. 
    
    Download the actual data set ( TrainingDataset.arff) file which consists of the 2456 records and attributes ( features)
    
    # Exercises for this week :
    
    a) Load the data set using Python numpy.genfromtxt function to numpy arrys
    b) Use the first 1250 records as training data set , use the last column as label for the classification 
    c) Use the last 1250 records as test data set
    d) Use the SVM to train
    e) Use the SVM to predict ( use the last 1200 records data)
    f) Findout the accuracy scores
    
    I have added a sample code in Phising_Predict.ipynb ( Jupyter node book file to download and run )
    

# Sample code :
    
import numpy as np
from sklearn import svm
from sklearn.metrics import accuracy_score

#load data 
training_data = np.genfromtxt('/Users/saravill/Exercise/Phising/TrainingDataset.arff', delimiter=',', dtype=np.int32)

inputs = training_data[:,:-1]
outputs= training_data[:, -1]

#split test data and train data

training_inputs = inputs[:1250]
training_outputs = outputs[:1250] 

testing_inputs = inputs[1250:]
testing_outputs = outputs[1250:]

#use SVM Classifier

classifier = svm.SVC()
classifier.fit(training_inputs, training_outputs)

#predict the last 1000+ reocrds 

predictions = classifier.predict(testing_inputs)

accu =accuracy_score(testing_outputs, predictions)
print (accu)

0.9036206017338093

    
  
 



