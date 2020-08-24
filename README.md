## This repo contains a notebook about a small test I am performing

It uses a plant disease dataset from kaggle.


We will understand the siamese network by building the plant disease model. The objective of our network is to understand whether two plants are similar or dissimilar.

Once we have our data as pairs along with their labels, we train our siamese network. From the image pair, we feed one image to the network A and another image to the network B. The role of these two networks is only to extract the feature vectors. So, we use two convolution layers with relu activations for extracting the features. Once we have learned the feature, we feed the resultant feature vector from both of the networks to the energy function which measures the similarity, we use Euclidean distance as our energy function. So, we train our network by feeding the image pair to learn the semantic similarity between them.

**What is Siamese Neural Network?**

Siamese Neural Network is a special type of neural network in first we train an image with a sequence of convolutional layers, pooling layers and fully connected layers we end up with a feature vector f(x1).
Then we train another image in the same sequence to get another feature vector f(x2). Now we compute d which will be the distance between each of the points in feature vector f(x1) with the feature vector f(x2).
If d is small we can tell both images are same else if d is large it’s the other way round.

![Fig 1: A Siamese Neural Network for Image Recognition](https://miro.medium.com/max/1068/1*V27gq7s7elBc8G52T8t1LQ.png)


**One-shot Image Recognition**

People may ask why have they used One-shot image recognition method though there are other state of art models like CNN and Hierarchical Bayesian Program Learning. The main reason for people using this method is the lack of data. The state of art Machine Learning Algorithms work very well when there is a huge amount of data but can fail miserably if there is a data scarcity.

In this method the model must make the correct prediction given only one example in each class in the training set. In this paper however the author has used more than one example for each class but it is very less compared to what the state of art algorithm requires.
