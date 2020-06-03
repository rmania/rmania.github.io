---
permalink: /machine_learning_models/
date: 2020-06-02
tags: [neural network, deep learning, neurons, layers]
header:
    overlay_image: "/images/machine_learning_models/neural_net_artistic_impression.png"
excerpt: "neural nets"
---

### Some terms and concepts 

> Neural networks are a beautiful biologically-inspired programming paradigm which enables a computer to learn from observational data - Michael Nielsen

Neural networks, consist of interconnected layers (so-called neurons), where some sort of mathematical calculations are performed. These neural nets (NN) can handle vast amounts of input and process it through multiple layers that learn increasingly complex features of the data at each layer. For example, once it learns what an object looks like, it can recognize the object in a new image.

At the heart of an NN is the unit (neuron) taking some kind of input variables, multiplying each one by a parameter (weight), adding the weighted inputs along with some bias value (1 for instance) and feeding it into some activation function. This output is then "fed" forward to the other layers in the network and there can be many (hence Deep Neural Networks or commonly referred to as Deep Learning). Each layer (or hidden layers as the layers between the input and output layers are called) tries to transform the feature values with the goal that the output at the end is the same as the target's value.

![neural_network](/home/diederik/projects/rmania.github.io/images/machine_learning_models/nn_simple_representation.jpg)

Neural nets 'learn' as follows: mostly NN's parameters are initialized as random values from a Gaussian (normal) distribution. Once an input or a set of inputs - called a batch- is "fed" through the NN, the outputted value is compared with the true values using a kind of loss function. This is called _forward propagation_. Next the algorithm goes back through the network in order to identify how much each parameter contributed to the error, a process called _backward propagation_. At each parameter the NN calculates how much each weight should be adjusted in order to improve the output and reduce the error. This process can be repeated multiple times (every time input are fed through is called an _epoch_) thereby iteratively updating the values of the parameters. 

NN's can get very complex. A great way to play around for yourself without coding is the [Tensorflow neural network playground](https://playground.tensorflow.org/#activation=tanh&batchSize=10&dataset=circle&regDataset=reg-plane&learningRate=0.03&regularizationRate=0&noise=0&networkShape=4,2&seed=0.72031&showTestData=false&discretize=false&percTrainData=50&x=true&y=true&xTimesY=false&xSquared=false&ySquared=false&cosX=false&sinX=false&cosY=false&sinY=false&collectStats=false&problem=classification&initZero=false&hideText=false). You can also download a free ebook [here](http://neuralnetworksanddeeplearning.com/index.html) from Michael Nielsen that I quoted above. He's able like no other to explain complex concepts about NN's in a clear and concise manner.