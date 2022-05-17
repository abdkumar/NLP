<h1>Fake News Classifier</h1> <br>
Develop a machine learning program to identify when an article might be fake news. Run by the UTK Machine Learning Club.

<h3> Data </h3>
Download data from https://www.kaggle.com/competitions/fake-news/data <br>

<p>
train.csv: A full training dataset with the following attributes: <br>

id: unique id for a news article <br>
title: the title of a news article <br>
author: author of the news article <br>
text: the text of the article; could be incomplete <br>
label: a label that marks the article as potentially unreliable <br>
1: unreliable <br>
0: reliable <br>
test.csv: A testing training dataset with all the same attributes at train.csv without the label. <br>

submit.csv: A sample submission file
</p>

<h3> Evaluation Metric </h3>
The evaluation metric for this competition is accuracy, a very straightforward metric.

![image](https://user-images.githubusercontent.com/29776259/168751017-a18ab27f-efd9-49ed-bf95-378e2b3d29aa.png)

Accuracy measures false positives and false negeatives equally, and really should only be used in simple cases and when classes are of (generally) equal class size
