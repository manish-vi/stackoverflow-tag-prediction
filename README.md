# Stackoverflow Tag Prediction

# 1. Business Problem

### 1.1 Description
<!-- <p style='font-size:18px'><b> Description </b></p> -->
Stack Overflow is the largest, most trusted online community for developers to learn, share their programming knowledge, and build their careers.

Stack Overflow is something which every programmer use one way or another. Each month, over 50 million developers come to Stack Overflow to learn, share their knowledge, and build their careers. It features questions and answers on a wide range of topics in computer programming. The website serves as a platform for users to ask and answer questions, and, through membership and active participation, to vote questions and answers up or down and edit questions and answers in a fashion similar to a wiki or Digg. As of April 2014 Stack Overflow has over 4,000,000 registered users, and it exceeded 10,000,000 questions in late August 2015. Based on the type of tags assigned to questions, the top eight most discussed topics on the site are: Java, JavaScript, C#, PHP, Android, jQuery, Python and HTML.


### 1.2 Problem Statemtent
<!-- <p style='font-size:18px'><b> Problem Statemtent </b></p> -->
Suggest the tags based on the content that was there in the question posted on Stackoverflow.

<p style='font-size:18px'>Source: <a href="https://www.kaggle.com/c/facebook-recruiting-iii-keyword-extraction/">https://www.kaggle.com/c/facebook-recruiting-iii-keyword-extraction/</a></p>


### 1.3 Source / useful links

 - Data Source : <a href="https://www.kaggle.com/c/facebook-recruiting-iii-keyword-extraction/data">https://www.kaggle.com/c/facebook-recruiting-iii-keyword-extraction/data
 - Youtube : <a href="https://youtu.be/nNDqbUhtIRg">https://youtu.be/nNDqbUhtIRg</a>
 - Research paper : <a href="https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/tagging-1.pdf">https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/tagging-1.pdf </a><br>
 - Research paper : <a href="https://dl.acm.org/citation.cfm?id=2660970&dl=ACM&coll=DL">https://dl.acm.org/citation.cfm?id=2660970&dl=ACM&coll=DL</a>

### 1.4 Real World / Business Objectives and Constraints

 - Predict as many tags as possible with high precision and recall.
 - Incorrect tags could impact customer experience on StackOverflow.
 - No strict latency constraints.

# 2. Machine Learning problem

## 2.1 Data

### 2.1.1 Data Overview

Refer: <a href="https://www.kaggle.com/c/facebook-recruiting-iii-keyword-extraction/data">https://www.kaggle.com/c/facebook-recruiting-iii-keyword-extraction/data</a>

All of the data is in 2 files: Train and Test.<br />

<pre>
<b>Train.csv</b> contains 4 columns: Id,Title,Body,Tags.<br />
<b>Test.csv</b> contains the same columns but without the Tags, which you are to predict.<br />
<b>Size of Train.csv</b> - 6.75GB<br />
<b>Size of Test.csv</b> - 2GB<br />
<b>Number of rows in Train.csv</b> = 6034195<br />
</pre>
The questions are randomized and contains a mix of verbose text sites as well as sites related to math and programming. The number of questions from each site may vary, and no filtering has been performed on the questions (such as closed questions).<br />
<br />

### 2.1.2 Data Field Explaination

Dataset contains 6,034,195 rows. The columns in the table are:<br />
<pre>
<b>Id</b> - Unique identifier for each question<br />
<b>Title</b> - The question's title<br />
<b>Body</b> - The body of the question<br />
<b>Tags</b> - The tags associated with the question in a space-seperated format (all lowercase, should not contain tabs '\t' or ampersands '&')<br />
</pre>

## 2.2 Mapping the real-world problem to a Machine Learning Problem

### 2.2.1 Type of Machine Learning Problem

It is a multi-label classification problem.<br>
<b>Multi-label Classification</b>: Multilabel classification assigns to each sample a set of target labels. This can be thought as predicting properties of a data-point that are not mutually exclusive, such as topics that are relevant for a document. A question on Stackoverflow might be about any of C, Pointers, FileIO and/or memory-management at the same time or none of these.


### 2.2.2 Performance metric

  - <b>Micro-Averaged F1-Score (Mean F Score) </b>: 
The F1 score can be interpreted as a weighted average of the precision and recall, where an F1 score reaches its best value at 1 and worst score at 0. The relative contribution of precision and recall to the F1 score are equal. The formula for the F1 score is:

        F1 = 2 * (precision * recall) / (precision + recall)

    In the multi-class and multi-label case, this is the weighted average of the F1 score of each class. <br>

  - <b>Micro f1 score: </b><br>
Calculate metrics globally by counting the total true positives, false negatives and false positives. This is a better metric when we have class imbalance.
<br>

  - <b>Macro f1 score: </b><br>
Calculate metrics for each label, and find their unweighted mean. This does not take label imbalance into account.

    <a href="https://www.kaggle.com/wiki/MeanFScore">https://www.kaggle.com/wiki/MeanFScore</a> <br>
    <a href="http://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html">http://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html</a><br>
    
 - <b> Hamming loss </b>: The Hamming loss is the fraction of labels that are incorrectly predicted. <br>
https://www.kaggle.com/wiki/HammingLoss <br>


## Getting Started
Start by downloading the project and run "StackOverFlow_Tag_Prediction.ipynb" file in ipython-notebook.

## Prerequisites
You need to have installed following softwares and libraries before running this project.
1. Python 3: https://www.python.org/downloads/
2. Anaconda: It will install ipython notebook and most of the libraries which are needed like sklearn, pandas, seaborn, matplotlib, numpy and scipy: https://www.anaconda.com/download/

## Libraries
* __scikit-learn:__ scikit-learn is a Python module for machine learning built on top of SciPy.
    * pip install scikit-learn
    * conda install -c anaconda scikit-learn

* __nltk:__ The Natural Language Toolkit (NLTK) is a Python package for natural language processing. 
    * pip install nltk
    * conda install -c anaconda nltk
    

## Authors
•	Manish Vishwakarma - Complete work  
