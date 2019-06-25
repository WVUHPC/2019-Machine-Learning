---
title: "Introduction"
start: 540
teaching: 30
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---
FIXME

Our experience in solving a problem by using a computer always involve the idea that we have access to the data at the same time that you can define some specific rules that can be used to map
an asswer. From a programming perspective, you need to create a series of rules that guarantee that given the input you will get the correct output. As the diversity of input and ouput makes this programming scheme to fail. A different approach is based on allowing the machine to learn, which means that experience will be used to make accurate predictions. This paradigm can be summarized as:

<a href="{{ page.root }}/fig/Figure1.Introduction.001.jpeg">
  <img src="{{ page.root }}/fig/Figure1.Introduction.001.jpeg" alt="Machine Laerning paradigm" />
</a>

In this new approach of solving problems in the computer, then our concern is to be able to create a model that will take the input and output and, by training a model, meaning allowing the computer to learn and extract the corrrelations between the data provided, we can create find the model parameters that represent the rules and can make a prediction (we infer the rules in this learning process). The model parameters can be found by using past information, where the input and outpuf is completely known. Here it is important to stress that the quality and size of the available data is the key to have a very good performance of the machine learning algorithm. 

While in the classical approach, we use a computer language, we code the program with the rules that provide the right answer, we then compile the program and use it to predict an answer based on new data . In the case of the machine learning, our purpose is to optimize parameters.

The fields where this methodology have an impact are very broad and the range from voice recognition, document or music classification, material structure prediction, fraud detection, recommendation systems, etc.

Machine learning are usually categorized in supervised learning and unsupervised learning. In the first case, we have access to data that can be classified and labeled and used for training of the algorithm. With the predicted parameters, the algorithm can infer the output from a given input. One the other hand, unsupervised machine learning algorithms are useful when the available data can not be (or it is not) classified or labeled. The methodology will explore the data to infer the correlations or hidden function from the provided data. Recently, there is also the development of the so called reinforcement machine learning algorithms, which are methologies that additionally to the provided data, it can also interact with the environment. This interaction produces actions that can lead to errors or rewards that can maximize the algorithm performance.

In reality, there is a large seet of learning problems and it will be really hard to include all of them in a single tutorial. That is why we have done a preselection of a broad number of possible problems:

1) Classification. Given a set of items, the algorithm should be able to classify them. The possible classification items is the one that will make the choice of the algorithm, but in general the number of possibilities needs to be small. Though there are problems as text classification or speech recognition where the number of possibilities is unbouded.

2) Regression. In this problem, we are interested in predicting the outcome by providing an input. This case can be unbounded as in the inputs as well as in the prediction.

3) Ranking. By providing a set of items, the algorithm should be able to order them according to some criteria. 

4) Clustering. Creating limits  between data that can define clear regions that separate them.

5) Association rule learning. Infer association pattern between the provided data.

6) Structure output. Organizing the input data in a more organized structure.

7) Dimensionality reduction. Here the algorithm reduced the dimensionality of the input into a lower dimensionality representation but keeping the most relevant properties of the initial representation.

In this tutorial, we will make use of two different open source libraries, which contain all the methods we will be describing in this tutorial but at the same time, contain more algorithms than those discussed here. Basically, we will use Sciki-Learn (https://scikit-learn.org/stable/) and TensorFlow (https://www.tensorflow.org/). We will only focuse on problems (1), (2), (4) and (5). 

{% include links.md %}
