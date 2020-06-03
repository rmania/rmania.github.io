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

Every day, there are more applications that rely on neural networking techniques in fields as diverse as healthcare, finance, human resources, retail, and self-driving cars. As for existing applications, the results have been steadily improving. 

At the heart of an NN is the unit (neuron) taking some kind of input variables, multiplying each one by a parameter (weight), adding the weighted inputs along with some bias value (1 for instance) and feeding it into some activation function. In the image below you can see some activation functions with fancy abbreviations like "relu" (Rectified Linear Unit), "softmax" and "cross-entropy" that have some desirable properties. The generated output of each layer is then "fed" forward to other layers in the network and there can be many (hence Deep Neural Networks or commonly referred to as Deep Learning). Each layer (or hidden layers as the layers between the input and output layers are called) tries to transform the feature values with the goal that the output at the end is the same as the target's value.

```markdown
![neural_network](/home/diederik/projects/rmania.github.io/images/machine_learning_models/neural_network_simple_representation.png){:class="img-responsive" height="700px" width="400px"}
```

[^Simple visual representation of a NN]: _Simple visual representation of a neural network

Neural nets 'learn' as follows: mostly NN's parameters are initialized as random values from a Gaussian (normal) distribution. Once an input or a set of inputs - called a batch- is "fed" through the NN, the outputted value is compared with the true values using a kind of loss function. This is called _forward propagation_. Next the algorithm goes back through the network in order to identify how much each parameter contributed to the error, a process called _backward propagation_. At each parameter the NN calculates how much each weight should be adjusted in order to improve the output and reduce the error. This process can be repeated multiple times (every time input are fed through is called an _epoch_) thereby iteratively updating the values of the parameters. 

NN's can get very complex and there many parameters to tune. A great way to play around for yourself without coding is the [Tensorflow neural network playground](https://playground.tensorflow.org/#activation=tanh&batchSize=10&dataset=circle&regDataset=reg-plane&learningRate=0.03&regularizationRate=0&noise=0&networkShape=4,2&seed=0.72031&showTestData=false&discretize=false&percTrainData=50&x=true&y=true&xTimesY=false&xSquared=false&ySquared=false&cosX=false&sinX=false&cosY=false&sinY=false&collectStats=false&problem=classification&initZero=false&hideText=false). You can also download a free ebook [here](http://neuralnetworksanddeeplearning.com/index.html) from Michael Nielsen that I quoted above. He's able like no other to explain complex concepts about NN's in a clear and concise manner.

### Major model types

The simplified explanation above refers to a **Convolution Neural Network** (CNN): a multi-layered NN with an setup designed to extract increasingly complex features of the data at each layer to determine the output to do Image Classification taks e.g. These techniques tend to work well if you unstructured data sets , say images, and you need to infer properties. With this you can diagnose health diseases from medical scans for instance. There are many more health AI related [use cases](https://healthitanalytics.com/news/top-5-use-cases-for-artificial-intelligence-in-medical-imaging)

Another major model type in the deep learning space are the **Recurrent Neural Networks** (RNNs). These are multi-layered NNs storing information in context nodes, which allows them to learn data sequences and output a number or another sequence. You would use this typically when you have specific sequenced datasets like time-series, audio recordings or text.  An RNN neuron receives a command that indicates the start of a sentence and not a set of independent input variables like in CNN's. Some use cases include: generate captions for images, predicting customers for a cinema (using **Long short**-**term memory** (LSTM) algorithms) or assess the likelihood that a credit-card transaction is fraudulent. 



### Breakthroughs

Examples of deep learning is how Apple can automatically organize photos, identify faces or, how Google can programmatically translate many languages with extreme accuracy. It is infusing deep learning into more and more products so you basically use it without knowing: Search, Maps, translation, YouTube, their self-driving cars etc. Let's go over some recent breakthroughs in various fields: 

**Natural Language Processing - NLP** where advanced language models using deep learning techniques can estimate a the probability distribution of a set of linguistic units and predict the next word in a sequence of words. These features are interesting and can be built at little cost and have significantly improved several NLP tasks such as [machine translation](https://en.wikipedia.org/wiki/Machine_translation), and [speech recognition](https://en.wikipedia.org/wiki/Speech_recognition).

Somewhere end of 2018, the Google AI unit launched BERT: **B**idirectional **E**ncoder **R**epresentations from **T**ransformers for Language Understanding gaining very promising results in fields like sentiment analysis and question and answering techniques. They open-sourced their code (based on the TensorFlow framework) on [Github](https://github.com/google-research/bert) and you can even try out one of their models to predict Movie Review sentiment on their Google [Colab environment](https://colab.research.google.com/github/google-research/bert/blob/master/predicting_movie_reviews_with_bert_on_tf_hub.ipynb).

Fortunately there are also some inspiring close-to-home examples like the City of Amsterdam that applies object recognition techniques to identify garbage or graffiti in the city of Amsterdam. [link](https://medium.com/maarten-sukel/garbage-object-detection-using-pytorch-and-yolov3-d6c4e0424a10)

_more examples_ W.I.P.

NN's and especially deep networks need considerable computing power in order to train. A normal CPU, i.e. on your laptop will not suffice unless your NN is really small. A **GPU** (Graphical Processing Unit) is designed to quickly render high-resolution images and video concurrently. As stated, Neural networks have had many developments on the algorithmic side recently, but the key to pushing model performance lies in taking full advantage of these GPUs, including the use of multi-GPU systems for training the networks. This is very hard because not every algorithm is designed for parallelization to let GPUs on separate systems share the burden. Another advantage of using multiple GPUs, even if you do not parallelize algorithms, is that you can run multiple algorithms or experiments separately on each GPU. Efficient hyper-parameter search (finding the best parameters mix for the best model outcome) is a common use of multiple GPUs in Deep Learning. The players in this field are NVIDIA, AMD, Intel and Google's Cloud Tensor Processing Units ([TPUs](https://cloud.google.com/tpu/docs/tpus)) 