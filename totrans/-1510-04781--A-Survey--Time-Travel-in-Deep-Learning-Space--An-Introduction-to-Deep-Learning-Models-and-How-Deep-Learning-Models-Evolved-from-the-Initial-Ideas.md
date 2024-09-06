<!--yml
category: 未分类
date: 2024-09-06 20:09:27
-->

# [1510.04781] A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas

> 来源：[https://ar5iv.labs.arxiv.org/html/1510.04781](https://ar5iv.labs.arxiv.org/html/1510.04781)

# A Survey: Time Travel in Deep Learning Space:
An Introduction to Deep Learning Models
and How Deep Learning Models Evolved from the Initial Ideas

Haohan Wang and Bhiksha Raj

Language Technologies Institute
School of Computer Science
Carnegie Mellon University
Pittsburgh, PA 15213
{haohanw, bhiksha}@cs.cmu.edu 

###### Abstract

This report will show the history of deep learning evolves. It will trace back as far as the initial belief of connectionism modelling of brain, and come back to look at its early stage realization: neural networks. With the background of neural network, we will gradually introduce how convolutional neural network, as a representative of deep discriminative models, is developed from neural networks, together with many practical techniques that can help in optimization of neural networks. On the other hand, we will also trace back to see the evolution history of deep generative models, to see how researchers balance the representation power and computation complexity to reach Restricted Boltzmann Machine and eventually reach Deep Belief Nets. Further, we will also look into the development history of modelling time series data with neural networks. We start with Time Delay Neural Networks and move further to currently famous model named Recurrent Neural Network and its extension Long Short Term Memory. We will also briefly look into how to construct deep recurrent neural networks. Finally, we will conclude this report with some interesting open-ended questions of deep neural networks.

###### Contents

1.  [1 Introduction](#S1 "In A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
2.  [2 From the Very Beginning to Neural Network](#S2 "In A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    1.  [2.1 Connectionism and Early Stage of Artificial Neural Network](#S2.SS1 "In 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [2.1.1 Connectionism](#S2.SS1.SSS1 "In 2.1 Connectionism and Early Stage of Artificial Neural Network ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        2.  [2.1.2 Early Stage Pioneers](#S2.SS1.SSS2 "In 2.1 Connectionism and Early Stage of Artificial Neural Network ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        3.  [2.1.3 Perceptron in Neural Network](#S2.SS1.SSS3 "In 2.1 Connectionism and Early Stage of Artificial Neural Network ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    2.  [2.2 Perceptron as a Principal Component Analyzer](#S2.SS2 "In 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [2.2.1 Perceptron](#S2.SS2.SSS1 "In 2.2 Perceptron as a Principal Component Analyzer ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        2.  [2.2.2 Perceptron as a Principal Component Analyzer](#S2.SS2.SSS2 "In 2.2 Perceptron as a Principal Component Analyzer ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    3.  [2.3 Neural Network, Backpropagation, Global Optimum and Universal Approximation](#S2.SS3 "In 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [2.3.1 Neural Network](#S2.SS3.SSS1 "In 2.3 Neural Network, Backpropagation, Global Optimum and Universal Approximation ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        2.  [2.3.2 Backpropagation](#S2.SS3.SSS2 "In 2.3 Neural Network, Backpropagation, Global Optimum and Universal Approximation ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        3.  [2.3.3 Universal Approximation Power](#S2.SS3.SSS3 "In 2.3 Neural Network, Backpropagation, Global Optimum and Universal Approximation ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
3.  [3 Neural Networks Extended to Deep Discriminative Models](#S3 "In A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    1.  [3.1 The Necessity of Depth](#S3.SS1 "In 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [3.1.1 Natural Motivation](#S3.SS1.SSS1 "In 3.1 The Necessity of Depth ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        2.  [3.1.2 Computation Efficiency](#S3.SS1.SSS2 "In 3.1 The Necessity of Depth ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        3.  [3.1.3 Computation vs. Statistics](#S3.SS1.SSS3 "In 3.1 The Necessity of Depth ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    2.  [3.2 Stacked Autoencoders](#S3.SS2 "In 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [3.2.1 Autoencoder](#S3.SS2.SSS1 "In 3.2 Stacked Autoencoders ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        2.  [3.2.2 Stacked Autoencoders](#S3.SS2.SSS2 "In 3.2 Stacked Autoencoders ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        3.  [3.2.3 Layerwise Initialization (Pretraining)](#S3.SS2.SSS3 "In 3.2 Stacked Autoencoders ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        4.  [3.2.4 Stacked Sparse Autoencoders](#S3.SS2.SSS4 "In 3.2 Stacked Autoencoders ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        5.  [3.2.5 Stacked Denoising Autoencoders](#S3.SS2.SSS5 "In 3.2 Stacked Autoencoders ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    3.  [3.3 Convolutional Neural Network](#S3.SS3 "In 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [3.3.1 CNN Architecture](#S3.SS3.SSS1 "In 3.3 Convolutional Neural Network ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        2.  [3.3.2 Convolutional Layer](#S3.SS3.SSS2 "In 3.3 Convolutional Neural Network ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        3.  [3.3.3 Subsampling Layer](#S3.SS3.SSS3 "In 3.3 Convolutional Neural Network ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        4.  [3.3.4 Relevant Techniques](#S3.SS3.SSS4 "In 3.3 Convolutional Neural Network ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    4.  [3.4 Dropout & Maxout](#S3.SS4 "In 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [3.4.1 Dropout](#S3.SS4.SSS1 "In 3.4 Dropout & Maxout ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        2.  [3.4.2 Maxout](#S3.SS4.SSS2 "In 3.4 Dropout & Maxout ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
4.  [4 Deep Generative Models](#S4 "In A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    1.  [4.1 Self Organizing Map](#S4.SS1 "In 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    2.  [4.2 Generative (Deep) Network Family](#S4.SS2 "In 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    3.  [4.3 Hopfield Network](#S4.SS3 "In 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [4.3.1 Energy of Hopfield Network](#S4.SS3.SSS1 "In 4.3 Hopfield Network ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        2.  [4.3.2 Application of Hopfield Network](#S4.SS3.SSS2 "In 4.3 Hopfield Network ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        3.  [4.3.3 Learning of Hopfield Network](#S4.SS3.SSS3 "In 4.3 Hopfield Network ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    4.  [4.4 Boltzmann Machine](#S4.SS4 "In 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [4.4.1 Energy of Boltzmann Machine](#S4.SS4.SSS1 "In 4.4 Boltzmann Machine ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        2.  [4.4.2 Application of Boltzmann Machine](#S4.SS4.SSS2 "In 4.4 Boltzmann Machine ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        3.  [4.4.3 Learning of Boltzmann Machine](#S4.SS4.SSS3 "In 4.4 Boltzmann Machine ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    5.  [4.5 Restricted Boltzmann Machine](#S4.SS5 "In 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [4.5.1 Traditional Learning of RBM](#S4.SS5.SSS1 "In 4.5 Restricted Boltzmann Machine ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        2.  [4.5.2 Contrastive Divergence](#S4.SS5.SSS2 "In 4.5 Restricted Boltzmann Machine ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    6.  [4.6 Deep Belief Networks](#S4.SS6 "In 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [4.6.1 Fine-tune for Generative Model](#S4.SS6.SSS1 "In 4.6 Deep Belief Networks ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        2.  [4.6.2 Fine-tune for Discriminative Model](#S4.SS6.SSS2 "In 4.6 Deep Belief Networks ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
5.  [5 Learning Through Time: Modeling Time Series Data](#S5 "In A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    1.  [5.1 Time Delay Neural Network](#S5.SS1 "In 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    2.  [5.2 Recurrent Neural Network](#S5.SS2 "In 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [5.2.1 Backpropagation Through Time](#S5.SS2.SSS1 "In 5.2 Recurrent Neural Network ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    3.  [5.3 Long Short Term Memory](#S5.SS3 "In 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
        1.  [5.3.1 Training of LSTM](#S5.SS3.SSS1 "In 5.3 Long Short Term Memory ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    4.  [5.4 Deep Recurrent Neural Networks](#S5.SS4 "In 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
6.  [6 Advantages and Disadvantages of Deep Learning](#S6 "In A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    1.  [6.1 Theoretically Best So Far](#S6.SS1 "In 6 Advantages and Disadvantages of Deep Learning ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
    2.  [6.2 Some Critical Flaws](#S6.SS2 "In 6 Advantages and Disadvantages of Deep Learning ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")
7.  [7 Conclusion](#S7 "In A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")

## 1 Introduction

This report is an introduction of deep learning models. Different from other deep learning tutorial, this report aims to draw a very comprehensive and yet brief picture about how these deep learning models are developed. It is comprehensive because is covers a lot of initial ideas about network models, like basic Neural Network, Self Oraganizing Map, Time Delay Neural Network. Yet it is brief because we cannot introduce everything about deep learning models due to the fast development of this field.

In this report, we will first trace back to the very beginning of how researchers start to model brain. With a belief of connectionism, a premier notion of neural networks is formed. Further, artificial neural networks are introduced with the successful design of perceptrons and backpropagation algorithm and start to play a dominating role in machine learning area.

With the background of early stage work, the Section 3 is devoted to some famous discriminative deep learning models. From the necessity of depth of models, we first move to stacked autoencoders and then introduce convolutional neural networks and some of its infinitely many optimizing techniques. Most of these techniques could be generalized to other deep learning models.

Section 4 is devoted to generative models. Again, we travel through a long journey from the early stage work like self organizing map and Hopfield network, to the middle age Boltzmann Machine and Restricted Boltzmann Machine, and to nowadays Deep Belief Nets, which is a natural extension of earlier work.

Then, Section 5 is a collection of neural network models for time series data, or generally sequential data. As a pioneer, Time Delay Neural Network is introduced first, followed by Recurrent Neural Network and the famous model called Long Short Term Memory (LSTM). Then, an intuition of how these models could be benefited from deep representation learning is introduced at the end of that section.

Last but not least, Section 6 is about some other interesting topics of deep learning and some topics that are yet to be fully explored when this report is prepared. Here, we will actually show some validation for the claim that deep learning is the best model so far. However, we will also see some flaws of the deep learning, that may possibility hinder its further development.

## 2 From the Very Beginning to Neural Network

### 2.1 Connectionism and Early Stage of Artificial Neural Network

This very first section is devoted to the very initial stage of Artificial Neural Network. It is built on people’s one point of view of understanding human mental phenomena: connectionism. The remaining is about the pioneer work of neural network modeling, how the information is passed and stored in the network and the early mathematics model. These works may not be directly useful for understanding neural network. However, we believe this whole process will be helpful for the researchers who are interested in pushing the deep learning work forward.

#### 2.1.1 Connectionism

It is a long way for researchers and philosophers to go in understanding how human brain and neural system function. Finally, they end up in two different, yet both interesting tracks: connectionism [[10](#bib.bib10)] and computationalism[[8](#bib.bib8)]. Needless to mention that which path is more promising or which path is the subset of the other, here we only focus on the connectionism points of view, where people believe that human intellectual abilities can be explained with a network of very simple units (neuron).

#### 2.1.2 Early Stage Pioneers

![Refer to caption](img/d7319c1ca961d8c879260b749e0b42bc.png)

Figure 1: An example of Bain’s neural groupings structure. (Figure from [[1](#bib.bib1)])

Relevant work started in 19th century. To make it easier to understand, it starts out as a philosophy question, rather than a computer science problem or a biology problem.

Alexander Bain first mentioned the connectionism ideas in [[1](#bib.bib1)]. Even earlier, he offered an interpretation of mental phenomena within an association framework. Then, in his book, he argues a brand new point of view stating memory is a model capable of ”putting required stuff together” rather than ”storing everything beforehand”. He named this memory structure as ”neural groupings”, as a predecessor of ”neural network” in our world, and further explained that under his view, connected nerve fibers are channeled to different parts of the network under different simulations.

As a very simple example, showed in Figure [1](#S2.F1 "Figure 1 ‣ 2.1.2 Early Stage Pioneers ‣ 2.1 Connectionism and Early Stage of Artificial Neural Network ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"). $X$, $Y$, $Z$ is triggered by different combinations of simulations from $a$, $b$ or $c$.

Bain’s work is recognized as the earliest work of discovering neural networks of human brain, however, Bain was not convinced by himself and argued that this structure shows no practical value.

Donald O. Hebb was influenced by Bain. In 1949, he stated the famous rule: ”Cells that fire together, wire together” [[18](#bib.bib18)], which emphasized on the activation behavior of co-fired cells. This theory attempts to explain neural groupings theory and provides a biological basis for learning methods in the rehabilitation of memory. In a more formal way, it says that when an axon of cell A is near enough to excite cell B and repeatedly or persistently takes part in firing it, some growth process or metabolic change takes place in one or both cells such that A’s efficiency as one of the cells firing B is increased. Mathematically, it could be written as:

|  | $\displaystyle\Delta\omega_{i}=\eta x_{i}y$ |  | (1) |

for the changes of synaptic weights.

The weight of neurons/connection units get updated with this learning rule, indicating that the connection of two signals is magnified every time when they appear together, which is consistent with our daily experience as human.

#### 2.1.3 Perceptron in Neural Network

As these pioneers successfully brought the connectionism and neural groupings into the world, other researchers started to work to complete the whole theory. One important completion is Frank Rosenblatt’s thoughts on how the information is stored and transferred in neural network.

In [[41](#bib.bib41)], he raised three questions regarding perceptrons: how perceptrons can help to 1)detect information, 2)store information and 3)recognize something with the information.

The first question is quite clear. The answer to it belongs to some work within the sensing field, thus this is irrelevant with this report. As for the following two questions, inspired by the connestionism, Rosenblatt believes that simple logic and boolean algebra cannot explain the phenomenon very well and he preferred probability theory. He made several assumptions to the model accounting for randomness, plasticity and similarity and he proposed a model of perceptron with S-points (as input), A-units (as activation function in model neural networks) and R-cells (as output). The model is showed in Figure [2](#S2.F2 "Figure 2 ‣ 2.1.3 Perceptron in Neural Network ‣ 2.1 Connectionism and Early Stage of Artificial Neural Network ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas").

![Refer to caption](img/2a17080541d3e1ec9fd3e27bc3c69192.png)

Figure 2: An illustration of Rosenblatt’s model of perceptron (Figure from [[41](#bib.bib41)])

### 2.2 Perceptron as a Principal Component Analyzer

After some historical points of views that built the foundation of neural network and deep learning previously, we can talk about computer science stuff now. Here, we will talk about the most basic unit of a neural network: the neurons. First, we will introduce perceptron, as the most basic neuron, then introduce the reasoning that a perceptron is basically a principal component analyzer.

#### 2.2.1 Perceptron

A linear perceptron builds from the assumption that the data labels we are interested in can be (approximately) represented by linear combination of the features. Thus, it can only make decision based on linear boundaries. A linear perceptron is shown as Figure [3](#S2.F3 "Figure 3 ‣ 2.2.1 Perceptron ‣ 2.2 Perceptron as a Principal Component Analyzer ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas").

![Refer to caption](img/2f9efc74a6808bb714d0436b7a56de46.png)

Figure 3: A linear perceptron

In Figure [3](#S2.F3 "Figure 3 ‣ 2.2.1 Perceptron ‣ 2.2 Perceptron as a Principal Component Analyzer ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), vector $\xi$ stand for the features of a data, $\mu$ are the weights corresponding to each feature, a perceptron takes the linear combination of features and make decision by comparing the weighted sum to a threshold. The weights and threshold are the parameters of this perceptron, learnt through machine learning. How do these weights get learnt? A simple weight update function is designed according to Hebbian learning rule, following the idea cells that fire together, wire together. Refer to Section [2.1](#S2.SS1 "2.1 Connectionism and Early Stage of Artificial Neural Network ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") for details.

With the basic understanding of linear perceptron, other non-linear neurons can be easily generalized with other forms of activation functions replacing linear thresholds. A sigmoid function is one of the most famous ones. When other functions are applied, simple updating rule may not be the best choice. Gradient descent is frequently adopted to update the weights.

#### 2.2.2 Perceptron as a Principal Component Analyzer

Now, let’s focusing on an interesting theory that when a perceptron is trained, the weights are updated in such a way that principal components of the data are extracted. In other words, a perceptron is actually doing the job of a Principal Component Analyzer [[36](#bib.bib36)].

Before we start, let’s make sure we are on the same page for PCA [[40](#bib.bib40)]. PCA is used to describe the data set with a series of principal components, where each principal component maximizes its variance and orthogonal to each other. There are three points of views to see PCA:

1.  1.

    It maximizes the variance of principal component, as showed in following:

    |  | $\displaystyle var$ | $\displaystyle=(Xu)^{T}(Xu)$ |  |
    |  | $\displaystyle u$ | $\displaystyle=\arg\!\max_{u^{T}u=I}(var)=(Xu)^{T}(Xu)=u^{T}X^{T}Xu$ |  |
    |  | $\displaystyle u$ | $\displaystyle=\arg\!\max_{u^{T}u=I}u^{T}Cu$ |  |

2.  2.

    It minimizes the reconstruction error, as showed in following:

    |  | $\displaystyle E$ | $\displaystyle=\sum_{i}&#124;&#124;x_{i}-(x_{i}u)u&#124;&#124;^{2}$ |  |
    |  |  | $\displaystyle=\sum_{i}(x_{i}^{T}x_{i})-2(x_{i}u)x_{i}^{T}u+(x_{i}u)^{2}u^{T}u$ |  |
    |  |  | $\displaystyle=\sum_{i}(x_{i}^{T}x_{i})-2(x_{i}u)^{2}+(x_{i}u)^{2}$ |  |
    |  | $\displaystyle u$ | $\displaystyle=\arg\!\min_{u^{u}=I}E=\arg\!\min_{u^{u}=I}-\sum_{i}(x_{i}u)^{2}=\arg\!\max_{u^{T}u=I}u^{T}Cu$ |  |

3.  3.

    Components are eigenvectors and the first component is the eigenvector corresponding to largest eigenvalues of covariance matrix. as showed in following:

    |  | $\displaystyle L$ | $\displaystyle=u^{T}Cu-\lambda(u^{T}u-I)$ |  |
    |  | $\displaystyle\dfrac{\partial L}{\partial u}$ | $\displaystyle=2Cu-2\lambda u=0$ |  |
    |  | $\displaystyle Cu$ | $\displaystyle=\lambda u$ |  |

It is interesting and quite trivial to see that these three views are equivalent.

Now Let’s start from the perceptron in Figure [3](#S2.F3 "Figure 3 ‣ 2.2.1 Perceptron ‣ 2.2 Perceptron as a Principal Component Analyzer ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"). All the functions above are summarized into the middle circle.

With these notations, a decision can be made through the following function:

|  | $\displaystyle\eta=\sum_{i}^{n}\mu_{i}\xi_{i}$ |  | (2) |

and according to hebbian hypothesis, the weights of this perceptron can be updated through the following equation:

|  | $\displaystyle\mu_{i}(t+1)=\dfrac{\mu_{i}(t)+\gamma\eta(t)\xi_{i}(t)}{\sqrt{\sum_{i}(\mu_{i}(t)+\gamma\eta(t)\xi_{i}(t))^{2}}}$ |  | (3) |

where it is the basic hebbian learning rule with a normalization term of L2 norm of the equation.

Then, a new law is introduced [[37](#bib.bib37)], where we assume the gain coefficient is small and don’t consider second terms, like following:

|  | $\displaystyle\mu_{i}(t+1)=\mu_{i}(t)+\gamma\eta(t)(\xi_{i}(t)-\eta(t)\mu_{i}(t))+O(\gamma^{2})$ |  | (4) |

With this function, the growth of weights is controlled with internal feedback.

Now, we look into the problem with a matrix point of view:

|  | $\displaystyle\mu(t+1)=\dfrac{\mu(t)+\gamma\eta(t)\xi(t)}{&#124;&#124;\mu(t)+\gamma\eta(t)\xi(t)&#124;&#124;_{2}}$ |  | (5) |

same as above, we now have:

|  | $\displaystyle\mu(t+1)$ | $\displaystyle=\mu(t)+\gamma\eta(t)(\xi(t)-\eta(t)\mu(t))+O(\gamma^{2})$ |  | (6) |
|  | $\displaystyle\mu(t+1)$ | $\displaystyle=\mu(t)+\gamma(\xi(t)\xi(t)^{T}\mu(t)-\mu(t)^{T}\xi(t)\xi(t)^{T}\mu(t)\mu(t))+O(\gamma^{2})$ |  | (7) |

now, let’s put it into continuous domain, so that we can take derivative there, and let’s take it with some more realistic assumptions for $\xi(t)$, as following:

|  | $\displaystyle\dfrac{d}{dt}z(t)=Cz(t)-(z(t)^{T}Cz(t))z(t)$ |  | (8) |

here, $C$ is the covariance matrix of $\xi(t)$. Now we can see that the eigenvectors of $C$ are the solution when we try to maximize the rule updating function. Since $z(t)$ are the eigenvectors of the covariance matrix of $\xi(t)$, we can get the conclusion that $z(t)$ are the principal components of the data. This step can be formally proved with Theorem 2.4 in [[16](#bib.bib16)], here we don’t discuss about it.

### 2.3 Neural Network, Backpropagation, Global Optimum and Universal Approximation

Here, let’s put neurons together and talk about neural networks. We will also show its training algorithm, the famous backprogapation and some of its interesting properties ¹¹1Due to the limit of space, some interesting properties are not covered here, for detailed topics like when neural network is guaranteed to have a global optimal, or when neural network is worse than a simple linear perceptron, please refer to the online version: http://haohanw.blogspot.com/2014/12/ml-my-journal-from-neural-network-to_15.html. At last, let’s have a look at the most famous fact of neural network, its power of universal representation.

#### 2.3.1 Neural Network

![Refer to caption](img/fde7263d2115fd9d54ef4729705653e2.png)

Figure 4: A typical two layer neural network. Input layer does not count as the number of layers of a network

When we connect many neurons into a network of neurons, we basically get a neural network. Figure [4](#S2.F4 "Figure 4 ‣ 2.3.1 Neural Network ‣ 2.3 Neural Network, Backpropagation, Global Optimum and Universal Approximation ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") shows a typical network, as we can see, more than random connection, the network has a layerwise architecture. Input layer takes input data and output layer makes prediction.

#### 2.3.2 Backpropagation

As we know, a single neuron can update its weights during learning through a gradient descent of its error function, backpropagation algorithm is a more generalized situation where we have many more neurons connected layerwisely and the error of a neuron need to be propagated back to the neurons of former layers, unless, of course, current neuron is of the first layer. Neurons of each layer update its weights according to the propagated error.

Let’s try to look at this problem formally. We have data $X$ and its golden standard $y$, and a network $N=[l_{1},l_{2},l_{3}...]$. We first apply the network to the data and get its error as:

|  | $\displaystyle E=\dfrac{1}{2}\sum(N_{i}X-y)^{2}$ |  | (9) |

Then calculate the error term for the last layer:

|  | $\displaystyle\delta_{ni}=\dfrac{\partial N_{i}X-y}{\partial l_{ni}}$ |  | (10) |

Propagate error of layer $n$ to former layer and calculate the error term at layer $n-1$

|  | $\displaystyle\delta_{n-1,i}=\dfrac{\partial\sum_{k}w_{n-1,i,n,j}\delta_{n,j}}{\partial l_{n-1,i}}$ |  | (11) |

Then we update the weights according to error term

|  | $\displaystyle w_{n-1,i,n,j}=w_{n-1,i,n,j}+\eta\delta_{n,j}x_{n,j}$ |  | (12) |

Since this report is mainly about deep learning, we don’t want to spend too much space for mundane topics for traditional backpropagation. The above derivations should be enough to have an understanding of deep learning. For more information, please refer to the original paper [[46](#bib.bib46)]

#### 2.3.3 Universal Approximation Power

Now, let’s move to a famous and exciting claim of neural network: a two layer neural network can represent any hypothesis space, it is also known as the universal approximation.

Before everything, two points need to be made clear. The first one is, as showed in the title, a neural network can only approximate any function, but cannot represent the exact function. The second one is that ”any function” actually means any continuous function, not functions with sudden jumps.

Although the formal proof of this approximation power is non trivial, we can look at this problem very intuitively. For now, let’s only consider the linear neurons, which builds the most basic foundation. Neurons with sigmoid squashing output should be easy to understand once the foundation ideas are showed.

Any single linear neuron can be learnt to represent a linear function, as showed in Figure [5](#S2.F5 "Figure 5 ‣ 2.3.3 Universal Approximation Power ‣ 2.3 Neural Network, Backpropagation, Global Optimum and Universal Approximation ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), two learnt linear function from two neurons.

![Refer to caption](img/40f802e075993b48319dbf61c3756ec2.png)

Figure 5: Two learnt linear functions with two independent neurons

![Refer to caption](img/bb3fadde868e786cfb4d172c6190e4fb.png)

Figure 6: A linear combination of two neurons to make a box function

In Figure [6](#S2.F6 "Figure 6 ‣ 2.3.3 Universal Approximation Power ‣ 2.3 Neural Network, Backpropagation, Global Optimum and Universal Approximation ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), we can see that a linear combination of two neurons can be learnt to represent a box function. Now, we have a box function, of which, the width is controlled by linear combination, and height is controlled by each of neuron. All of these parameters can be learnt through data. Therefore, we can learn any box function with two neurons. Further more, when the width is approximating to 0, we can learn to represent any point with two neurons. Since any function is a set of points, we can approximate any function. This approximation only requires one hidden layer, every pair represents the two basic neuron of a box function, the output layer will combine them linearly.

This theory can be proved more formally [[25](#bib.bib25)] [[5](#bib.bib5)], but we don’t cover them here.

## 3 Neural Networks Extended to Deep Discriminative Models

After some background information in the previous section, now let’s start to move to the domain of deep learning. In this section, first we need to emphasis the necessity of depth for neural networks, which may sound controversial with previous mentioned theorem of universal approximation power. Then we will move to two famous discriminative models: Stacked Autoencoders and Convolutional Neural Networks. We will end this section with some optimizing techniques for Convolutional Neural Network, but these techniques can be extended to many other models (even some non-network typed models).

### 3.1 The Necessity of Depth

In Section [2.3.3](#S2.SS3.SSS3 "2.3.3 Universal Approximation Power ‣ 2.3 Neural Network, Backpropagation, Global Optimum and Universal Approximation ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), we have looked at neural network and talked about its universal approximation property. Then, an interesting question will be, since a neural network is already so powerful, why we need to move to deep learning.

The take home message here is that, for every one less layer of a neural network, it requires exponential more neurons to approximate the same function. However, the bottleneck of working on a shallow architecture is not simply the expense of computation of exponential more neurons, the requirement of exponential more training data to maintain the generalization ability is a fundamental unsolvable problem. Before that, there is also the most intuitive motivation: since one of the most fundamental goals of artificial intelligence is to simulate human intelligence, it’s reasonable to simulate the deep brain architecture with learning models (despite the fact that some learning models have already performed better than human). The rest is for a further explanation of these arguments, which is not critical in superficial understanding of deep learning.

#### 3.1.1 Natural Motivation

As we have talked, the natural motivation of going into deep architecture is that our human brain forms a deep architecture in recognition.

Although how brain functions still remains as a mystery, people intuitively believe brain forms a hierarchical sensing of knowledge. This belief is validated with some state of art research, like Meunier et al [[33](#bib.bib33)], Perry et al ²²2http://www.cpri.ca/uploads/section000181/files/brain%20structure%20and%20function.pdf. We don’t have to go into the details of these ideas, since these are not the focuses of a deep learning report.

#### 3.1.2 Computation Efficiency

To understand the computation efficiency of a deep architecture compared to a shallow architecture, let’s look at the computation of circuits. As we know, a two layer circuit of logic gates can be used to represent any boolean functions, which can be written as either sum of products (disjunctive normal form) or product of sums (conjunctive normal form). Further, Hastad [[17](#bib.bib17)] has proposed that there are functions computable in polynomial size and depth $k$ but requires exponential size when the depth is restricted to $k-1$.

Now, let’s move from circuits theory to the networks domain with sum product network. A sum product network is an analogy of circuits logic gates in the neural network field, where there are two basic computation neurons. A sum neuron is an unit that computes the weighted sum of inputs and a product neuron is an unit that computes the product of inputs. In [[7](#bib.bib7)], Delalleau et al defined a shallow architecture as a sum product network with only one hidden layer, and they defined a deep architecture as a network with more than two hidden layers. They introduced a network architecture, where sum layer and product layer stacks alternatively, and each computing neuron only takes in two inputs, as showed in Figure [7](#S3.F7 "Figure 7 ‣ 3.1.2 Computation Efficiency ‣ 3.1 The Necessity of Depth ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas").

![Refer to caption](img/3932d73c9d8dedcddf35dde8eb9d7552.png)

Figure 7: A two layer sum-product network. (Figure from the [[7](#bib.bib7)])

With these definition, and a series of derivation, they drew the conclusion that the functions that require $O(2^{n})$ of units with a shallow network can be represented with $O(n^{2})$ units with a depth of $O(logn)$ architecture.

Then, let’s move to traditional neural networks. In Section [2.3.3](#S2.SS3.SSS3 "2.3.3 Universal Approximation Power ‣ 2.3 Neural Network, Backpropagation, Global Optimum and Universal Approximation ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), we have seen that any functions can be approximated with a two layer neural network, in which the lower layer generates box functions (or points), the upper layer combines lower layer output. This serves as a good analogy of what has been showed in circuits theory. Further, a neuron is a linear combination of weights with an activation function. By linear combination, a neuron can easily simulate AND and OR relation with a proper set of weights and threshold. [[38](#bib.bib38)] proposed a formal theory of it and proved it.

#### 3.1.3 Computation vs. Statistics

Furthermore, when an inefficient representation of a function with shallow architecture is adopted, many more parameters are trained and computed. This will easily introduce the curse of dimensionality [[11](#bib.bib11)] with insufficient data set. Thus, even technology suddenly evolves and engineers find a way to compute exponential number of neurons, the problem of shallow architecture remains as a statistical problem rather than a computational one.

### 3.2 Stacked Autoencoders

After a long time of preparation, we finally step into the first deep learning architecture. Personally, we think autoencoder is the most simple and intuitive idea of neural networks, so let’s start with autoencoder and its deep learning version, stacked autoencoders.

#### 3.2.1 Autoencoder

Everything about an autoencoder[[31](#bib.bib31)] is disclosed by its name. ”Auto” means an unsupervised learning process, and ”encoder” means it learns a coding mechanism (or a representation) of data. Like any other coding mechanism, the learnt representation is expected be simpler than data itself. Therefore, an autoencoder is a feedforward network that can learn a compressed, distributed representation of data, usually with goal of dimensionality reduction. An autoencoder usually has one hidden layer between input and output layer. Hidden layer usually has a more compact representation than input and output layers, i.e. hidden layer has fewer units than input or output layer. Input and output layer usually have the exact same setting, which allows an autoencoder to be trained unsupervisedly with same data fed into input layer and compared at output layer. The training process is the same as traditional neural network with backpropagation, the only difference lies in the error is computed by comparing output to the data itself, rather than supervised labels.

![Refer to caption](img/41629e087800c409269afede02fa1d64.png)

Figure 8: Tom Mitchell’s example of an autoencoder, (Figure from [[34](#bib.bib34)])

Figure [8](#S3.F8 "Figure 8 ‣ 3.2.1 Autoencoder ‣ 3.2 Stacked Autoencoders ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"). shows my favourite example of an autoencoder, from Tom Mitchell’s book [[34](#bib.bib34)]. As we can see, the input and output are exactly the same: they are an inefficient representation of eight mutually exclusive labels with bits. An autoencoder learns a compact representation with 3 hidden units. With a proper threshold applied, the learnt representation is the same as the compact bit representation of eight labels. Different from traditional neural networks, what matters in an autoencoder is the representation learnt by hidden layer, rather than the predicted result generated by output layer.

#### 3.2.2 Stacked Autoencoders

As its name discloses, a stacked autoencoders is what we get when we stack a pile of autoencoders together. For every layer, its input is the learnt representation of former layer and it learns a more compact representation of the existing learnt representation. Thus a stacked autoencoder will have a pyramidal architecture.

Alternatively, we can think a stacked autoencoders as half of one multi-hidden-layer autoencoder, in which there are $2n-1$ hidden layers, formed with two identical $n$ layer pyramidal architecture connected top layer to top layer. These two top layers merge into one layer since they are identical, thus there are only $2n-1$ hidden layers altogether, as showed in Figure [9](#S3.F9 "Figure 9 ‣ 3.2.2 Stacked Autoencoders ‣ 3.2 Stacked Autoencoders ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas").

![Refer to caption](img/c85775bd3116dad1ea12d18f8a5ac43f.png)

Figure 9: A autoencoder with many hidden layers (two stacked autoencoders)

Since what we are interested in is only the bottom half of what is showed in Figure [9](#S3.F9 "Figure 9 ‣ 3.2.2 Stacked Autoencoders ‣ 3.2 Stacked Autoencoders ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), then how is stacked autoencoders different from any traditional pyramidal structure neural networks? To answer this question, let’s first look at a fundamental problem when training a deep neural network with backpropagation.

#### 3.2.3 Layerwise Initialization (Pretraining)

There are several problems when training a deep network with backpropagation algorithm. First, when the error is backpropagated, it becomes minuscule in the first several layers and training will not converge to anywhere within a large number of steps. This will cause the network to learn to reconstruct the average of all the training data. However, this problem could be mitigated when a layerwise learning rate is introduced, allowing lower layers to be trained with smaller learning rates. Another problem is that the target space is a non-convex one with many local minimums, with random initialization, backpropagation will often result in an unsatisfying local minimum. Thus, the network trained is often useless.

This also explains the reason why deep networks, though apparently able to perform better, cannot outperform shallow architectures until layerwise initialization (pretraining) is introduced in 2006[[20](#bib.bib20)]. Erhan et al[[9](#bib.bib9)] have introduced more about the advantages of layerwise pretraining with experiments, mainly for the sake of optimization (as we have discussed) and regularization. Layerwise pretraining is very critical in deep learning and we will visit this idea again and again in the future.

This is the reason why we need to think our pyramidal architecture deep neural networks as a stacked autoencoders: we can perform layerwise pretraining. For every hidden layer $h_{1}$, we unsupervisedly train it with its input and an output of identical settings with input. Then, we discard the output and stack hidden layer $h_{2}$ onto it. Where $h_{2}$ will take $h_{1}$ as input, and get trained with an output layer with the same setttings of $h_{1}$. Then, again the output layer of $h_{2}$ is removed, another hidden layer $h_{3}$ is stacked. Same steps repeat until we build enough layers.

#### 3.2.4 Stacked Sparse Autoencoders

Once we have built stacked autoencoders, one choice of next step is to think whether we could learn a compacter representation with existing topology. Some sparsity controls are introduced into the autoencoders to learn a sparse representation. Interestingly, with sparsity regularization the architecture of the stacked autoencoders may not necessarily be a pyramid, because regularization will be able to force autoencoders to learn a more concise representation than last layer. Thus, although sparse autoencoders are designed to learn a compact representation from a different mechanism, the shared goal (compact representation) of sparse autoencoders and traditional autoencoders leads to an equivalent performance of these two.

#### 3.2.5 Stacked Denoising Autoencoders

As we have seen in Section [2.2](#S2.SS2 "2.2 Perceptron as a Principal Component Analyzer ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), an autoencoder trained with squared error criterion is basically a Principle Component Analysis, (when it is trained with other criterion, it is other well defined statistical characteristics of the data set) this is clearly not a desirable solution. We build a deep network to simulate human brain and we expect our deep network could learn some generalization, rather than purely statistics.

In order to train a network with generalization, stacked autoencoders are introduced. Its algorithm is as simple as its intuition: human brain is able to discard the noises as it learns a generalized model. The algorithm is also very simple, every time when a new layer is trained, the data at input layer is replaced with noised data while the data at output layer stays the same. By doing this, we expect the autoencoders can learn a more generalized and compact representation of data.

### 3.3 Convolutional Neural Network

Here let’s have a look at the earliest successful architecture of deep network, the convolutional neural network, also known as LeNet (because of its inventor). Let’s look at its basic settings and try to understand some reasoning together with the experimental findings.

#### 3.3.1 CNN Architecture

Inspired by biological understanding of visual cortex, convolutional neural network is proposed based on the foundation of traditional multiple layer perceptrons. It is first proposed by LeCun et al in 1998 [[29](#bib.bib29)], where it got its name LeNet.

Even from the beginning of CNN, it is very different from traditional neural networks. As researches of all these years go, more and more techniques have been introduced with better test results. Here let’s start with the very beginning architecture in the first paper as showed in Figure [10](#S3.F10 "Figure 10 ‣ 3.3.1 CNN Architecture ‣ 3.3 Convolutional Neural Network ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas").

![Refer to caption](img/087d59c50452717187d5e03920ef8a92.png)

Figure 10: Architecture of LeNet-5, one of the first initial architectures of CNN. (Figure from [[29](#bib.bib29)])

As showed in Figure [10](#S3.F10 "Figure 10 ‣ 3.3.1 CNN Architecture ‣ 3.3 Convolutional Neural Network ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), the network first apply convolution operation and subsampling operation alternatively to the input data, with computation units called convolutional layers and subsampling layers respectively. After two groups of such computation, the representation of data in higher layers are fed into a fully connected traditional neural networks, where it finishes its task of a classification problem.

With this architecture, it introduces several advantages compared to traditional neural networks.

1.  1.

    Sparsity: CNN is more computation efficient than a traditional neural network. It is sparse in two ways:

    1.  *

        Sparse Connection: A computation unit of layer l is only connected to a certain number of local units of layer l-1, rather than traditional full connection across all the units of two layers.

    2.  *

        Sparse Representation: All the units share the same set of weights connecting from the former layer.

2.  2.

    Translation invariance: CNN is more robust towards varies of input features. This property also comes in two points of views:

    1.  *

        On convolution layer: convolution is a computation with the property of translation invariance, a network implemented convolution will inherit this property.

    2.  *

        On subsampling layer: with the common sampling method: max-pooling, this layer is also translation invariant, because max is a computation that is invariant to rearranges of input features.

#### 3.3.2 Convolutional Layer

In order to understand convolutional layer, let’s first have a look at how matrix convolution works and its effect on image processing.

We are familiar with the convolution defined on one dimensional functions, it is basically the same when it comes to two dimensional matrices, as showed in Figure [11](#S3.F11 "Figure 11 ‣ 3.3.2 Convolutional Layer ‣ 3.3 Convolutional Neural Network ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas").

![Refer to caption](img/b109941c9cf8cd2c8fc69b72ecd7f22b.png)

Figure 11: An example of matrix convolution

As showed in Figure [11](#S3.F11 "Figure 11 ‣ 3.3.2 Convolutional Layer ‣ 3.3 Convolutional Neural Network ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), the leftmost matrix is the input matrix, the middle one is usually called kernel matrix. Convolution is applied to these matrices and the result is showed as the rightmost matrix. The convolution process is a element-wise product followed by a sum, as showed in the example. When the left upper 3x3 matrix is convoluted with the kernel, the result is 1\. Then we slide the target 3x3 matrix one column right, convoluted with the kernel and get the result 3\. We keep sliding and record the results as a matrix. Because the kernel is 3x3, every target matrix is 3x3, thus, every 3x3 matrix is convoluted to one digit and the whole 5x5 matrix is shrunk into 3x3 matrix. (Because 5 - (3-1) = 3\. The first 3 is the size of kernel matrix. )

Convolutional layer is a layer that does this job. However, different from traditional designed-kernel image processing, CNN learns the kernel all by backpropagation. The most amazing fact is that, the kernels learnt are usually some meaningful kernel like edge detection designed by human. Using multiple feature maps (computation units) in one convolution layer allows a better combination of kernels to be trained. For instance, in some real world example, a set of edge detection kernel can be trained, with different responsibilities like horizontal edge detection, vertical edge detection.

#### 3.3.3 Subsampling Layer

Subsampling is an easier process. It is even easier when we only consider one sampling method for now: max-pooling. It also has a kernel matrix like convolutional layer, but unlike convolutional layer, the computation is as simple as max. It is a simple but important computation.

It is responsible for reducing the size of data, thus, reduce computation complexity. Besides, as we have talked above, max is a translation invariant process, it allows CNN to be translational invariant.

#### 3.3.4 Relevant Techniques

Now, since we have an idea about CNN, let’s move further to see some examples that can make CNN works better.

Activation Function is an important and interesting topic for neural networks. A good selection of an activation function can make a big difference in the performance of a neural network for a certain tasks. Even deep networks are much more sophisticated, this situation remains the same. There is a variety of activation functions, like step function, sigmoid, tanh, softmax, or some complex ones that can capture the desired s-curve shape, or some ones that may not even capture the shape, but somehow work. Some famous examples are as following:
1) Hyperbolic tangent function

|  | $f(x)=\tanh x=\dfrac{e^{x}-e^{-x}}{e^{x}-e^{-x}}$ |  |

2) Sigmoid function

|  | $f(x)=\dfrac{1}{1+e^{-x}}$ |  |

3) Rectifier function [[6](#bib.bib6)]

|  | $f(x)=x*I(x>0)$ |  |

4) Capped Rectifier function. (where $C$ is a constant)

|  | $f(x)=\min(x*I(x>0),c)$ |  |

These functions are usually implemented after one pair of convolutional layer and subsampling layer, take pooling result as input and fire output to next convolutional layer or fully connection layer. Among these functions, the most interesting one for CNN is probably ReLu.

ReLu (Rectified Linear Units) is an interesting activation function. It allows the network to compute much faster than a network with sigmoid or tanh as activation functions because it is simply a max operation. More importantly, it allows sparsity of the network since when initialized randomly, around half of the whole network will be 0\. Sparsity plays a critical role in deep networks, since it can introduce the advantages like information disentangling, efficient variable-size representation, linear separability etc [[14](#bib.bib14)].

Because of these advantages, ReLu usually plays a role more than just an activation functions integrated into pooling layer. Researchers start to use it as a layer between convolutional layer and subsampling layer, as this demo³³3http://cs.stanford.edu/people/karpathy/convnetjs/demo/mnist.html shows. More than this, some network are built around this idea, like [[6](#bib.bib6)]. These works are beyond the domain of this report.

It should be simple to notice that the discontinuity of ReLu at $0$ may hurt the performance of backpropagation. However, [[45](#bib.bib45)] has showed that, empirically, ReLu works better than other activation functions like softmax, although theoretically it remains an open question.

Pooling Function is used in the subsampling layer to shrink the size of data. Max-pooling comes as the commonest technique probably because it is simple and intuitive. The max of the input features may help the performance of network to the best, but sometime the average of features also works. Therefore, besides max-pooling, there is also one average-pooling.

Besides, [[30](#bib.bib30)] once proposed an idea of probabilistic pooling, where they constrain the pooling process follows a rule that at most of the target unit is on. Thus, the pooling result will be the same as any one of the target unit or it could be nothing. (In comparison, max-pooling always trigger the unit with max value while average-pooling always trigger all the unit and take average of them)

Also, how the pooling area is selected can be a question. [[28](#bib.bib28)] applies overlapping pooling instead of traditional pooling where the target areas of pooling can overlap each other.

Learning rate is important in controlling the convergence of gradient based methods. To select an appropriate learning rate is a challenging question. Some smart solutions can be adopted like decreasing learning rates as iteration increases, or training lower layers with greater learning rates and upper layers with smaller learning rates.

### 3.4 Dropout & Maxout

Now let’s look at the details of a famous technique called dropout together with another similar technique called maxout. Again, these techniques are not constrained only to convolutional neural networks, but can be applied to almost any deep networks, or even non-network models.

#### 3.4.1 Dropout

Dropout is famous, and powerful, and simple. Despite the fact that dropout is widely used and very efficient, the idea is actually simple: randomly dropping out some of the units while training. One case can be showed as in the Figure [12](#S3.F12 "Figure 12 ‣ 3.4.1 Dropout ‣ 3.4 Dropout & Maxout ‣ 3 Neural Networks Extended to Deep Discriminative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")

![Refer to caption](img/3abd695f9977aa5a6b51c08b1b23b44b.png)

Figure 12: An illustration of the idea of dropout

To state this a little more formally: for each training case, each hidden unit is randomly omitted from the network with a probability of $p$. One thing to notice though, the selected dropout units are different for each training instance, that’s why this is more of a training problem, rather than an architecture problem.

As stated in the origin paper [[21](#bib.bib21)], another view to look at dropout makes this it more interesting. Dropout can be seen as an efficient way to perform model averaging across a large number of different neural networks, where overfitting can be avoided with much less cost of computation.

#### 3.4.2 Maxout

Maxout is an idea derived for dropout. It is simply an activation function that takes the max of input, but when it works with dropout, it can reinforce the properties dropout has: improve the accuracy of fast model averaging technique and facilitate optimization.

Different from max-pooling, maxout is based on a whole hidden layer that is built upon the layer we are interested in, so it’s more like a layerwise activation function. As stated in [[15](#bib.bib15)], with these hidden layers that only consider the max of input, the network remains the same power of universal approximation. The reasoning is not very different from what we did in Section [2.3.3](#S2.SS3.SSS3 "2.3.3 Universal Approximation Power ‣ 2.3 Neural Network, Backpropagation, Global Optimum and Universal Approximation ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") on universal approximation power.

Despite of the fact that maxout is an idea derived on dropout and works better, maxout can only be implemented on feedforward neural networks like multi-layer perceptron or convolutional neural networks. In contrast, dropout is a fundamental idea, though simple, that can work for basically any networks. Dropout is more like the idea of bagging, both in the sense of bagging’s ability to increase accuracy by model averaging, and in the sense of bagging’s widely adoption that can be integrated with almost any machine learning algorithm.

## 4 Deep Generative Models

Now let’s visit another family of machine learning models: generative model. In this section, we will first start with an early stage work called self organizing map, which will help us build some understanding of generative models. Then, with a summary of the relationships of generative models we start to visit Hopfield Field, Boltzmann Machine, Restricted Boltzmann Machine and Deep Belief Nets.

### 4.1 Self Organizing Map

![Refer to caption](img/115ce32d4e0aa3b105ae62f553d92218.png)

Figure 13: An example of Self Organizing Map

Self Organizing Map is a type of neural network invented by Kohonen in 1980s [[27](#bib.bib27)] that can be used to represent data with lower dimension, usually with one or two dimensions. It can be trained unsupervisedly, thus the techniques that we are familiar with, like backpropagation or gradient descent is not feasible here. The only thing that remains related to traditional networks is probably how the weights are updates. Figure [13](#S4.F13 "Figure 13 ‣ 4.1 Self Organizing Map ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") shows a typical Self Organizing Map in two dimension.

As showed in Figure [13](#S4.F13 "Figure 13 ‣ 4.1 Self Organizing Map ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), Self Organizing Map is a collection of nodes forming a structure of a lattice. All these nodes are fully connected to the input data. All the input nodes are combined together to represent one input vector, which is of the same length of the weight vector of each of the map node.

![Refer to caption](img/49d11dd2b209ec77d902a0dd0e2cb86e.png)

Figure 14: An example of Self Organizing Map representing color

Now, let’s have a look at how a two dimensional SOM can represent higher dimensional data. Figure [14](#S4.F14 "Figure 14 ‣ 4.1 Self Organizing Map ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") is an example when a map is used to represent a 10-dimension color space. As we can see, it looks like a result of clustering, where each color is represented locally.

More interestingly, it works more than representing different data points with a certain area of the map. Figure [15](#S4.F15 "Figure 15 ‣ 4.1 Self Organizing Map ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") shows how a two dimensional map changes its weights to represent a 3-dimensional shape.

![Refer to caption](img/06bc91e8e302db7e68f9b4d773c430aa.png)

Figure 15: A 3 dimensional shape (left) is represented by a two dimensional SOM (right) (Figure from [[27](#bib.bib27)])

Finally let’s conclude the topic of SOM by looking at its training algorithm. The idea is not very complex, but interestingly explains why it could represent data in such a way. As we have said before, the whole idea is not related with backpropagation or so. Some part of it looks like K-means, while some part of it looks like KNN classification. The training algorithm is as following:

1.  1.

    First initialization weights of each node randomly

2.  2.

    When iteration step $t$ does not exceed the maximum allowed steps, pick a random data vector $v$:

    1.  2.1

        Select the node with minimum Euclidean distance between node and data, this node is called Best Matching Unit. (BMU)

    2.  2.2

        Select the nodes of interest as the neighbors of BMU within distance of $r(t)$.

    3.  2.3

        Update nodes of interest (Node $i$) with the following equation:

        |  | $\displaystyle w_{i}(t+1)=w_{i}(t)+d_{i,bum}l(t)(v-w_{i}(t))$ |  | (13) |

where $w$ stands for the weights of these nodes, $d$ stands for a penalty related to the distance between current node and BMU. $l$ is learning rate, which decreases as iteration increases. $r$ is the radius to select nodes of interest, it also decreases as iteration increases.

With this training algorithm, SOM can be trained to represent data with lower dimensions.

### 4.2 Generative (Deep) Network Family

Now, we have briefly talked about the very first model in generative model family. Following this, there should come some other famous models, like Boltzmann Machine, Restricted Boltzmann Machine or Deep Belief Nets. Before that, let’s first look at some relationship between these three models another one called Hopfield Network. Figure [16](#S4.F16 "Figure 16 ‣ 4.2 Generative (Deep) Network Family ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") shows this relationship. In the figure, x-axis represents the representation power of each model and y-axis represents the computation complexity to perfectly train this model. It only shows this idea approximately.

![Refer to caption](img/2a4dbee9c8baf25de1974ef136fe4eca.png)

Figure 16: An approximation of computation complexity and representation power of each model

In Figure [16](#S4.F16 "Figure 16 ‣ 4.2 Generative (Deep) Network Family ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), we can see that there is a huge difference in the representation power, as well as computation complexity across all these four models. The following introduction will following the arrows in the figure across these models, when the underlining story is how we step by step, move to deep belief networks. First we start from Hopfield Network, which has a very limit representation power, yet it could be trained fast. Then researchers want their model to represent more knowledge, so Boltzmann Machine is born as a stochastic version of Hopfield Network. However, the problem is that there is no efficient way that can train it. Then, researchers start to make constraints, removing all the intra-layer connections lead to Restricted Boltzmann Machine. It’s more efficient, but the representation is worse as well. Then people start to stack RBM and make Deep Belief Nets, which has much more representation power, but also much more difficult to train it perfectly. Fortunately, layer wise initialization makes training feasible and that’s why DBN become popular. From now on, we will first look at Hopfield Network and Boltzmann Machine, then let’s move to Restricted Boltzmann Machine and Deep Belief Nets.

### 4.3 Hopfield Network

Hopfield Network is a recurrent network with binary units, proposed by John Hopfield in 1982 [[24](#bib.bib24)]. In the newtork, recurrent means that all the edges in this network are bidirectional and binary units are the units that can take either one of two values. (Mostly, these two values are 0 and 1, sometimes, it could be -1 and 1\. This difference is not just about representation, but also about how the energy is computed, thus about which configuration the network will converge to. As we may see briefly in the following text.)

![Refer to caption](img/acb42b9b17fd78d00a73b6f47f0a6e7f.png)

Figure 17: An example of Hopfield Network

Figure [17](#S4.F17 "Figure 17 ‣ 4.3 Hopfield Network ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") shows a very simple example of Hopfield Network, those numbers on the edge are the weights of the bidirectional edges, numbers in the circles represents the state of the units. Current setting is a stable state of this network. The values of weights are predefined, and we will talk about how these stable states of units are achieved after we talked about its energy.

In Hopfield Network, there is no such unit as input unit or output unit. Every unit can be fed in with data and every unit can serve as the input for other units.

#### 4.3.1 Energy of Hopfield Network

The energy of Hopfield Network can be defined as following:

|  | $\displaystyle E=\sum_{i}s_{i}b_{i}-\dfrac{1}{2}\sum_{i,j}s_{i}s_{j}w_{i,j}$ |  | (14) |

where $s$ stands for the state of a unit, $w$ stands for weight, $b$ stands for bias, we take half of the second term because it is a symmetric network. Here we introduce $b$ to make the equation more formal, but we don’t bother with it here. Therefore, when we ignores the bias term, the energy of the the network in Figure [17](#S4.F17 "Figure 17 ‣ 4.3 Hopfield Network ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") is -5\. This is the global minimum of energy of this network.

#### 4.3.2 Application of Hopfield Network

The goal of a Hopfield Network is to keep update its units to reach the minimum of energy, which could be used to represent memory. This memory has a very interesting application: it allows content addressable memory. If a Hopfield Network memorizes an event as the minimum of its energy, then if the event somehow gets corrupted or noised, we could recover all the event by feeding part of that event into this Hopfield Network, when it updates itself to the minimum of energy, those states of unit corresponds to the whole event.

As a very interesting analogy, we can think Hopfield Network memorizes the stable state for a ball in a bowl, as showed in Figure [18](#S4.F18 "Figure 18 ‣ 4.3.2 Application of Hopfield Network ‣ 4.3 Hopfield Network ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas")

![Refer to caption](img/2a21d8a6ebe73475e1eb45834bc39697.png)

Figure 18: An analogy of the memory in Hopfield Network

As basic physics tells us, no matter where the ball is placed initially, it will stop at the bottom of the ball stably, where it has the minimum of its energy.

However, Hopfield Network cannot keep the memory very efficient, because a network $N$ units can only store memory up to $0.15N^{2}$ bits. While a network with $N$ units have $N^{2}$ edges. Also, after storing $M$ memories, each connection has a integer value in range $[-M,M]$. Thus, the number of bits required to store $N$ units are $N^{2}log(2M+1)$. Let’s not worry about how these numbers are proved, for this report, they are used to show that Hopfield Network is not very efficient to store memory.

#### 4.3.3 Learning of Hopfield Network

Now let’s have a look at how Hopfield Network learns the states of its units. It basically follows the Hebbian Learning rule that we have talked about in Section [2.1](#S2.SS1 "2.1 Connectionism and Early Stage of Artificial Neural Network ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), ”Cells that fire together, wire together”, since the energy is calculated for each two units and the link between them. This also explains why weights are symmetric. There are two ways to update the unit.

Asynchronous update the unit with a random order, one by one. Each time we select a random unit and to test if switching the unit will result in decreasing the total energy. Then we adjust the unit and move to another unit randomly.

Synchronous update will first test each unit to see whether we should adjust its state according to the current setting. After testing all the units, make the adjustment. This may not even end up with decreasing the energy. Both of these two methods may lead to local minimum, oscillation or loop of states.

### 4.4 Boltzmann Machine

![Refer to caption](img/23f126bff73eb365de6fe2cbaef42df3.png)

Figure 19: An example of Boltzmann Machine

As Figure [19](#S4.F19 "Figure 19 ‣ 4.4 Boltzmann Machine ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") shows, it is a fully connection network with hidden units and visible units, where visible units can be fed in with data. This figure clearly shows why Boltzmann machine is a hidden unit version of Hopfield Network, then how about stochastic?

As we know, in the learning procedure of Hopfield Network, skipping out of local minimum will be tough. So, inspired from physics, a method to transfer state regardless current energy is introduced. For a certain unit, set it to state 1 regardless of current state with the following probability:

|  | $\displaystyle p=\dfrac{1}{1+e^{-\Delta E/T}}$ |  | (15) |

where $T$ stands for the temperature. This is inspired by a physics process where the higher the temperature is, the more likely the state will transfer. Besides, the probability of higher energy state transferring to lower energy state will be always greater than the reverse process. The higher the temperature $T$ is, the less contrast this difference is. This temperature idea is highly related to a very popular optimization algorithm called simulated annealing [[26](#bib.bib26)] back then, but we don’t have to talk about it here. The idea behind simulated annealing is similar to a technique about adjusting learning rate as backpropagation iteration increases. Here, to make this problem simpler, we only worry about the situation when temperature is a constant, for example, when $T=1$.

#### 4.4.1 Energy of Boltzmann Machine

Now let’s talked about the energy function of Boltzmann Machine. Similarly to Hopfield Network, the energy of BM is defined as following:

|  | $\displaystyle E(v,h)=-\sum_{i}v_{i}b_{i}-\sum_{k}h_{k}b_{k}-\dfrac{1}{2}\sum_{i,j}v_{i}v_{j}w_{i,j}-\dfrac{1}{2}\sum_{i,k}v_{i}h_{k}w_{i,k}-\dfrac{1}{2}\sum_{k,l}h_{k}h_{l}w_{k,l}$ |  | (16) |

where $v$ stands for visible units, $h$ stands for hidden units, $w$ stands for weights and $b$ stands for bias.

Based on this energy function, the probability of a joint configuration over both visible unit and hidden unit can be defined as following:

|  | $\displaystyle p(v,h)=\dfrac{e^{-E(v,h)}}{\sum_{m,n}e^{-E(m,n)}}$ |  | (17) |

The probability of only visible units (or hidden units) can be achieved by marginalizing this joint probability.

When Boltzmann Machine is trained to its stable state, which is called thermal equilibrium, the distribution of these probability will remain the same because the distribution of energy will remain the same. However, the probability for each visible unit or hidden unit may vary and the energy may not be at their minimum. This is related to how thermal equilibrium [[32](#bib.bib32)] is defined, where the only thing stays the same is the distribution of each part of the system.

#### 4.4.2 Application of Boltzmann Machine

Similar to Hopfield Network, Boltzmann Machine can be used to generate data. By marginalizing the joint probability of visible and hidden units, we can get the probability of visible units as the following function:

|  | $\displaystyle p(v)=\dfrac{\sum_{h}e^{-E(v,h)}}{\sum_{m,n}e^{-E(m,n)}}$ |  | (18) |

when the settings of a BM is learnt, we can easily apply this to the network and sample out the visible units.

#### 4.4.3 Learning of Boltzmann Machine

At last, let’s have a look at how to train this powerful Boltzmann Machine by maximizing the likelihood function. Because the probabilities are defined as the exponential term of energy, we try to maximize the sum of log probabilities instead to make it simpler. Now, when we take derivative of the log probabilities over weights, we can see a very beautiful term showed as following:

|  | $\displaystyle\dfrac{\partial\log p(v)}{\partial w}=<s_{i},s_{j}>_{data}-<s_{i},s_{j}>_{model}$ |  | (19) |

It is the difference between the expectation value of product of states while the data is fed into visible states and the expectation of product of states while no data is fed, both products are computed when the system reaches thermal equilibrium. Then the question is about how to get these two products.

The answer is as simple as sampling. Keep sampling all the possible states to until the system reaches its thermal equilibrium. There are several algorithms about this, but we believe the main idea remains the same as sampling. As long as this sampling procedure is not avoided or dramatically simplified, the learning of Boltzmann Machine remains a difficult problem.

### 4.5 Restricted Boltzmann Machine

Restricted Boltzmann Machine, invented by Smolensky in 1986 [[42](#bib.bib42)], is a Boltzmann Machine without intra-layer connection between units. In other words, there are only connections between visible units and hidden units, but no connections between visible units and visible units or between hidden units and hidden units. It is a bipartite graph, as showed in Figure [20](#S4.F20 "Figure 20 ‣ 4.5 Restricted Boltzmann Machine ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas").

![Refer to caption](img/6af8c88c8ac8601c0eadc6bd98770ea8.png)

Figure 20: An example of Restricted Boltzmann Machine

Because of the removal of some connections, the energy function also becomes simpler, as following:

|  | $\displaystyle E(v,h)=-\sum_{i}v_{i}b_{i}-\sum_{k}h_{k}b_{k}-\dfrac{1}{2}\sum_{i,k}v_{i}h_{k}w_{i,k}$ |  | (20) |

where, as usual, $v$ stands for visible units, $h$ stands for hidden units, $w$ stands for weights and $b$ stands for bias.

#### 4.5.1 Traditional Learning of RBM

Traditionally, training a RBM follows the same way as training a BM, but it gets much simpler because the removal of intra-layer connections. The adjust of weights is related to the difference of expectation of products of units with data fed in and the expectation of products of without data fed in, as before, as following:

|  | $\displaystyle\dfrac{\partial\log p(v)}{\partial w}=<s_{i},s_{j}>_{data}-<s_{i},s_{j}>_{model}$ |  | (21) |

One simpler thing is that, now we don’t have to sample the states one by one to get the thermal equilibrium. Since hidden units do not affect each other now, we can calculate the state of all hidden units within one step parallel. Then we reconstruct visible units, and then compute hidden units. This is Gibbs Sampling [[13](#bib.bib13)]. However, this only decreases the computation complexity in a sense that all hidden units (or visible units) can be calculated together, but there is not guarantee that how long it takes to get the thermal equilibrium state.

#### 4.5.2 Contrastive Divergence

Contrastive Divergence is an interesting idea, which states that we don’t have to keep working until thermal equilibrium. Usually, only a few steps of sampling is enough, sometimes, even one step is enough! (Here one step means first sample hidden states, adjust weights, then reconstruct the visible units, sample hidden units and then adjust weights again.)

This dramatically reduces the computation complexity of training an RBM, but why does this even work? It is only an empirical result when it is first introduced. It could be understood as an changes of error surface, where the first sampling drags down the error surface and the second sampling drags up the sampling to form a local optimum.

On the theoretical side, Bengio 2007 showed that contrastive divergence (k-step short Gibbs sampling) can obtain a biased but convergence estimator of log-likelihood gradient [[3](#bib.bib3)]. To cover this theory may require heavy work related with Gibbs sampling, so let’s skip it here.

One thing to notice: Contrastive Divergence is a biased approximation. It does not maximize the likelihood of the data under the model but the difference of two KL-divergences, like following:

|  | $\displaystyle KL(q&#124;p)-KL(q_{k}&#124;p)$ |  | (22) |

where $q$ is the empirical distribution and $p_{k}$ is the distribution of the visible variables after $k$ steps of the Markov chain. If the chain already reached stationarity it holds $p_{k}=p$ and thus $KL(p_{k}|p)=0$ and the approximation error of Contrastive Divergence vanishes.

### 4.6 Deep Belief Networks

Deep Belief Network is one of the models in the family of belief networks, which is a graph model with directed connections. For a long time, training a belief network is a big problem since there is no effective way to model the posterior probability with explaining away effect. However, in 2006, a breakthrough work[[20](#bib.bib20)] which makes training a deep belief network possible. That is the reason that DBN becomes so famous these days.

Deep Belief Network is a stacked RBM. The visible layer of the bottom RBM is fed in with data, and the hidden layer of the bottom RBM is served as the visible layer of the second RBM. Then, a third RBM can be stacked onto the second RBM by merging the visible layer of third RBM and the hidden layer of the second RBM. It could be stacked to as many as possible layers. A 3 layer DBN is showed in Figure [21](#S4.F21 "Figure 21 ‣ 4.6 Deep Belief Networks ‣ 4 Deep Generative Models ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas").

![Refer to caption](img/a9672f43dde41a3f9b4f26ac2def5418.png)

Figure 21: A three layer Deep Belief Network

Same as RBM, a DBN mainly serves as a generative model. When we use it to generate data, we first sample the top layers with Gibbs Sampling to reach its thermal equilibrium, then we pass the visible states of top layer top down to generate the data. This is why in the figure, weights are colored differently. Green arrows are part of the generative models while red arrows are only used for inference.

The breakthrough of how to train DBN is also a simple idea. (But why it works is very complex) The training falls into two steps: the first step is layer-wise pre-training and the second step is fine-tuning. Compared to how we train a neural network traditionally, the first step can also be seen as a clever way of initialization, the second step can be as simple as backpropagation, depends on what model we want to train.

The pre-training step follows the same idea of pre-training a stacked autoencoder. We first treat the bottom two layers as a standard RBM, perform contrastive divergence to train it. Then we move a layer higher, train the second RBM with contrastive divergence, until we finish training the top RBM.

Then, the only question remains is how to fine-tune the model, with different goals of generative model and discriminative model, we have different strategies.

#### 4.6.1 Fine-tune for Generative Model

Fine-tuning for a generative model is achieved with a contrastive version of wake-sleep algorithm. This algorithm is interesting because it is designed to interpret how brain works. Scientists have found that sleeping is a critical process of brain function and it seems to be an inverse version of how we learn when we are awake. The wake-sleep algorithm also has two steps. In wake phase, we propagate information bottom up to adjust top-down weights for reconstructing layer below. Sleep phase is the inverse of wake phase. We propagate the information top down to adjust bottom-up weights for reconstructing layer above.

The contrastive version of this wake-sleep algorithm [[19](#bib.bib19)] is that we add one contrastive divergence phase between wake phase and sleep phase. The wake phase only goes up to the visible layer of the top RBM, then we sample the top RBM with contrastive divergence, then a sleep phase starts from the visible layer of top RBM.

#### 4.6.2 Fine-tune for Discriminative Model

The strategy for fine-tuning a DBN as a discriminative model is our old friend: backpropagation. Since we have labels of data, we can apply standard backpropagation to the pre-trained DBN.

However, even we finally apply backpropagation to this network, pre-training is still necessary. By pre-training we can have many advantages like shortening the training time greatly and avoiding poor local optimums.

## 5 Learning Through Time: Modeling Time Series Data

Now, let’s travel back for the one last time. This time, we visit the development track of time series data modelling, or more generally, sequencial data modelling. From the beginning of Time Delay Neural Network, we are going to visit famous Recurrent Neural Network and one of this most famous and powerful variant: Long Short Term Memory (LSTM). At last, we will see how to build deep recurrent neural networks.

### 5.1 Time Delay Neural Network

Time Delay Neural Network is invented by Waibel in 1989 [[44](#bib.bib44)], it is interesting in the sense that it breaks the limit of traditional neural networks when they only consider the spacial information of data fed to the network. All the data fed in are treated as they occur at the same time and exist for the same period of time by the neural networks, although the features of data may represent different aspects of data of different timing. For example, we can separate a video to a set of frames and concatenate the these frames into one huge vector. This huge vector represents the information of the video with different time point, but when it is fed into a traditional neural network, the neural network only treats them as different information stored in different neurons. This may work sometime, but this is not perfect and that’s the reason that TDNN is invented. Figure [22](#S5.F22 "Figure 22 ‣ 5.1 Time Delay Neural Network ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") shows a typical TDNN, but actual TDNN vary a lot for different applications.

![Refer to caption](img/c4c947eeb0a545a9a79b3e97a001ae76.png)

Figure 22: A basic local architecture of Time Delay Neural Network (Figure from [[44](#bib.bib44)])

The architecture of Figure [22](#S5.F22 "Figure 22 ‣ 5.1 Time Delay Neural Network ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") can be seen as a two layer neural network with a complex connections between two layers, or it could also be seen as a single computation unit with only one complicated function that performs summing and thresholding.

As implied in the figure, it is an extension of a traditional neural network which only considers the sum and threshold of an input vector $u$. In a TDNN architecture, several delayed units are introduced. These delayed units are used on keep the information the features ahead. If we are considering features across $t$ steps, then we need $t-1$ delay units. The rest of this architecture only varies slightly from traditional neural network.

### 5.2 Recurrent Neural Network

Recurrent Neural Network[[12](#bib.bib12)] is a huge family, it is a complement set of traditional neural networks, which we call feed-forward network here. Actually, there should be more recurrent neural networks than feed forward network since RNN removes the constraint that the network only allows information to be passed forward (although another constraint is implied for RNN that there must be at least one feed backward edge in the network). However, in reality, most applications can be done well enough only considering feed forward networks, which leads to the fact that we don’t see Recurrent Neural Network so often. However, we are expected to see them a lot in the future because of the success of Deep Belief Networks and Restricted Boltzmann Machines, etc. Basically, every model we have met in the generative deep learning model section are recurrent neural networks since the edges are bi-directional. Let’s keep this to the simplest case, as showed in Figure [23](#S5.F23 "Figure 23 ‣ 5.2 Recurrent Neural Network ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas").

![Refer to caption](img/1be76d69a7d508bdc0c3fca82a18d556.png)

Figure 23: A typical example of Recurrent Neural Network

As showed in Figure [23](#S5.F23 "Figure 23 ‣ 5.2 Recurrent Neural Network ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), $x(t)$ stands for input layer, $s(t)$ is a hidden layer, $s(t-1)$ is another hidden layer, $y(t)$ is output layer. Layer $s(t-1)$ gets its input from $s(t)$ and also sends its output to $s(t)$, that this is how this Recurrent Neural Network works. The other parts except $s(t-1)$ works normally as a feed forward network, while $s(t-1)$ stores the information from $s(t)$ and feeds this stored information back to $s(t)$ to be considered as another input at next iteration. As indicated by its name, $s(t-1)$ serves as a unit that can remind $s(t)$ what its last state at last iteration is while $s(t)$ is making decisions at this iteration for the output layer.

#### 5.2.1 Backpropagation Through Time

Traditional backpropagation will not work for recurrent neural networks, for the reason that it requires a clear directed flow of information, so that it knows which direction is ”back” to propagate. In RNN, because we have feed back edges, it’s not possible to define a back direction. However, Backpropagation Through Time solves this problem. It is a simple extension of backpropagation for RNN. It first applies some modification of recurrent neural network to remove the loops of edges and then applies backpropagation on it. Figure [24](#S5.F24 "Figure 24 ‣ 5.2.1 Backpropagation Through Time ‣ 5.2 Recurrent Neural Network ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") shows a simple illustration on how to modify the network.

![Refer to caption](img/b969e71d6cfceb269306b796ceafd42b.png)

Figure 24: An illustration of the unfolding ideas of Backpropagation Through Time

As we can see in the figure, BPTT unfolds the recurrent neural network into a feed forward network, where each $s$ layer takes the input from input vectors at current iteration and output of $s$ layer from previous iteration. Also shown in the figure, all the weights $U$ share the same parameters because it is originally the same connection, the same applies weights $V$.

After BPTT unfolds RNN to a feed forward network, the only thing left is to apply backpropagation to this network. The only difference is that weights $U$ and $V$ are adjusted according to an aggregated differences of difference of each copy of $U$ or $V$.

One nature question could be, how far into history this BPTT should unfold the recurrent network. In the figure, it only unfolds back to 3 iterations ago. The trade off of selecting a proper length of history to consider should be obvious, the longer the history the model considers, the better the modelling usually is, but the more computation we need to afford and more complex error surface we are working on. In fact, recurrent neural networks already works on quite complex error surface to optimize. Gradient based solution applied here may suffer from more problems of local optimal than applied to feed forward neural network.

### 5.3 Long Short Term Memory

A typical recurrent neural networks may have a problem remembering inputs several iterations ahead, which means that the influence of a prior input may vanish as the followed up input mixes into the unit and washes out prior influence. Thus the influence of the prior input decays exponentially and this is not a desired property. To solve this problem, Long Short Term Memory recurrent neural network is proposed by Hochreiter et al in 1997 [[23](#bib.bib23)].

A unit of LSTM is designed to be very complex, as showed in Figure [25](#S5.F25 "Figure 25 ‣ 5.3 Long Short Term Memory ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas").

![Refer to caption](img/65673ddcc415353e535bd1521b4f4277.png)

Figure 25: A single computation unit for LSTM

The three GATE circles are three gates to control the behaviour of LSTM: it only takes new input when the input gate is open, only sends out output when output gate is open and it only keeps remembering its state when the forget gate is open. The middle circle is used for remembering its current state, with a self-directed edge, given that forget gate is open.

With this architecture, LSTM solves the vanishing gradient problem and has been successfully applied to many real world problems.

#### 5.3.1 Training of LSTM

Training of LSTM also follows the standard procedure of recurrent neural networks, which is Backpropagation Through Time. However, it has an advantage over traditional recurrent neural networks under this algorithm, which is that it can preserves the gradient error as it preserves input, such that vanishing gradient[[22](#bib.bib22)] problem is avoided.

### 5.4 Deep Recurrent Neural Networks

![Refer to caption](img/ceb264d021ad289fce3db8226b56069d.png)

Figure 26: Recurrent neural network with deep input architecture

![Refer to caption](img/210652fa1eb8d13f8513a039e9f26d75.png)

Figure 27: Recurrent neural network with deep hidden architecture

![Refer to caption](img/38f802a76313bdaee9f9beca6643572b.png)

Figure 28: Recurrent neural network with a deep output architecture

As we have talked previously, since there is no clear direction defined for recurrent neural network, it’s also hard to define a deep recurrent neural network itself. However, since a recurrent neural network is consist of three main components: input, hidden layer, output, as well as three main connections: input-hidden, hidden-hidden, hidden-output, it’s not hard to expand these basic components with the idea of deep learning, as Pascanu et al did [[39](#bib.bib39)]. We can see these three different deep recurrent neural networks in Figure [26](#S5.F26 "Figure 26 ‣ 5.4 Deep Recurrent Neural Networks ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") to Figure [28](#S5.F28 "Figure 28 ‣ 5.4 Deep Recurrent Neural Networks ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"). In those figures, blue layers are the original layers that a traditional recurrent neural network will have, grey layers are inserted to allow more abstract representation of certain knowledge, i.e. the layers that account for ”deep”. In the figure, $i(t)$ stands for input, $h(t)$ stands for hidden layer, $o(t)$ stands for output layer.

Figure [26](#S5.F26 "Figure 26 ‣ 5.4 Deep Recurrent Neural Networks ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") shows the simplest version of a deep recurrent neural network. By adding more layers on the input side, a deep RNN allows the hidden layer to learn a more abstract representation of input knowledge. However, this is simple because this is not directly related to recurrent neural network. This representation can be trained and learnt thorough any other deep architecture, like stacked autoencoders, deep belief networks, or even convolutional neural networks, independently from recurrent neural networks.

However, not every deep local architecture can be separated from recurrent neural network. Figure [27](#S5.F27 "Figure 27 ‣ 5.4 Deep Recurrent Neural Networks ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") shows an architecture that learns a better representation of hidden states, that it only works when effectively fed together with the next input.

The last basic combination is deep output layer as showed in the Figure [28](#S5.F28 "Figure 28 ‣ 5.4 Deep Recurrent Neural Networks ‣ 5 Learning Through Time: Modeling Time Series Data ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"). Usually we can think this as a multi-layer MLP, but deep generative models can also be used here.

So, these are three basic components for a deep recurrent neural networks. As we can see, they are all simple ideas derived from basic deep networks. A deep recurrent neural network can of course be an arbitrary combination of these three components. A cleverer combination can also be applied, like a combination of a deep and shallow architecture, resulting a ”bypass” connection passing information across layers.

## 6 Advantages and Disadvantages of Deep Learning

Now, let’s stop travelling back into the history and start to look forward into the future of deep learning. We all know that it’s the most popular machine learning domain so far, but how far it could reach? On one hand, some researcher believe that some traditional problems can be settled by deep learning once for all, for example, deep learning can almost recognizing MNIST data set as well as human being recognition. Figure [29](#S6.F29 "Figure 29 ‣ 6 Advantages and Disadvantages of Deep Learning ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") shows that it basically not possible for machine learning models to reach $100\%$ of recognition accuracy on MNIST data set. On the other hand, Szegedy et al[[43](#bib.bib43)] found some intriguing flaws of deep learning, that may lead to a disaster of this domain.

![Refer to caption](img/cac6b96580e5566f2bf3f0fd909860b8.png)

Figure 29: Some examples that are impossible to be recognized even by human in MNIST data set.

In this final section, let’s first talk about the bright side of deep learning with a comparison of the last famous algorithm: SVM, and then talk about some of its flaws.

### 6.1 Theoretically Best So Far

Let’s first look at a Hamlet story of machine learning world. Back in 1980s or early 1990s, Neural Network is like the king of machine learning domain. With a universal approximation power, as we talked in Section [2.3.3](#S2.SS3.SSS3 "2.3.3 Universal Approximation Power ‣ 2.3 Neural Network, Backpropagation, Global Optimum and Universal Approximation ‣ 2 From the Very Beginning to Neural Network ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"), and its intuitive advantage of simulating human brain, it is the favorite machine learning algorithm of researchers across every domain. All kinds of extensions have been proposed for different specific problems. However, the crown does not stay long. SVM, invented in late 1990s, soon replaced it. A plain SVM can works as well as a shallow neural network, and proper designed kernelized SVM can also serve as a universal approximation algorithm, but SVM works much faster than neural network. Then, around ten years later, deep learning comes back, as an advanced version of neural network to challenge the leading place of SVM. Basically, it could deprive SVM of leading position easily for the following reason.

According to Yann LeCun⁴⁴4http://www.kdnuggets.com/2014/02/exclusive-yann-lecun-deep-learning-facebook-ai-lab.html , SVM serves like a two layer neural network, where the first layer are support units, measuring the distance between input vector and support vectors and second layer serves as a linear combination of these distance. These distances are not limited to Euclidean, but any similarities that can be calculated with kernels. Yann believes that, deep learning can beat SVM easily simply because that deep learning has more layers, despite the fact that SVM usually searches for global optimum.

Caruana et al[[4](#bib.bib4)] has shown that, among all the popular machine learning algorithms, SVM and Random Forest are generally the best. Since deep learning is more promising than SVM, as we have talked, then how about Random Forest? Again, let’s answer this question by understanding algorithm with layers.

[[2](#bib.bib2)] has pointed that Random Forest has only one more layer than Decision Tree. A decision can be seen as a two layer classifier, of which the first layer is to match input vector to training data (leaves of a tree) and the second data serving as a linear combination of this exact match. Different of SVM, the second layer serves as a linear combination of exact match, so a decision tree has no power of generalizing knowledge to functions that are not represented by training data. Random Forest builds one more layer on its decision trees, thus it allows the classifier represent exponential more functions. The representation power of a Random Forest is still limited within 3 layers, though there seems no empirical proof to show that this 3-layer architecture is not good enough to compete deep learning.

### 6.2 Some Critical Flaws

Interestingly, while people keep discussing about how good a deep learning can be, some experimental results surprise human beings about how stupid it could be. Let’s look at Figure [30](#S6.F30 "Figure 30 ‣ 6.2 Some Critical Flaws ‣ 6 Advantages and Disadvantages of Deep Learning ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas"). How many cars are there in it?

![Refer to caption](img/a7f18067977308851023b7e081d60639.png)

Figure 30: Two objects that can be recognized differently by deep learning architecture.

Obviously, there are two. Interestingly, according to Szegedy et al’s finding [[43](#bib.bib43)], a deep learning architecture will believe that there is only one car because it thinks the left one is a car while the right one is something else, a truck, a horse, or even an orange.

To clarify, these two pictures are not exactly the same, there are little variations in many pixels of these images, but these variations are not noticeable by human eyes.

It’s already surprising enough that a deep learning cannot recognize these two pictures into same class. It is more surprising that this is a universal problem. Almost every deep network has these ”blind spots”. For every deep network, one can manually manipulate some pixels of a figure to make the network recognize this figure into something else.

Another interesting property that makes the power of deep learning controversial is raised by Nguyen et al [[35](#bib.bib35)]. They have showed that a state-of-art deep learning model trained by ImageNet, that can perform well on normal tasks, recognize non-recognizable images as familiar objects with a very high confidence. Figure [31](#S6.F31 "Figure 31 ‣ 6.2 Some Critical Flaws ‣ 6 Advantages and Disadvantages of Deep Learning ‣ A Survey: Time Travel in Deep Learning Space: An Introduction to Deep Learning Models and How Deep Learning Models Evolved from the Initial Ideas") shows some of such human generated noised images are recognized by deep neural networks.

![Refer to caption](img/88c19e31bb7ba38593345e6c41e09581.png)

Figure 31: Some human generated figures that are recognized as familiar objects with high confidence ($>99.6\%$)

This example shows us that although deep neural networks are generally believed to be the models that have the most promising chance to simulate human brain, there will be still a long way before neural networks can play the role human brain plays, despite the fact that these models behave quite well on certain tasks.

## 7 Conclusion

In this report, we have traced back to the very beginning of deep learning research and have reviewed how those deep learning models have evolved from the initial ideas to the powerful model of today.

Our road map follows the trace that, we start from how people start to pay attention to human brain and model brain as a connection of neurons. Then, this connection of neurons model is extended to nowadays neural network. With some knowledge of human visual system, convolutional neural network is developed as an extension of neural network, and as the pioneer member of deep learning family.

On the othe hand, Self Organizing Map is invented for representation learning. Following the generative model’s track, Hopfield Network leads to Boltzmann Machine, then leads to Restricted Boltzmann Machine. Finally RBM is stacked up to be the famous Deep Belief Nets these days.

Following the track of modelling sequential data, there are Time Delay Neural Network, Recurrent Neural Network and famous Long Short Term Memory. This report also reviewed deep recurrent neural network, which is a intuitive combination of deep networks and RNN.

Besides these history of evolution of different deep learning models, it also showed some interesting facts and future challenges of deep learning models. This report can help to understand of how these models are developed and help to contribute in developing new models.

## Acknowledgements

Thanks to the Professor Bhiksha Raj for the instruction during his lab course and thanks to the teaching assistant of that course, Zhengzhong Danny Lan⁵⁵5http://www.cs.cmu.edu/ lanzhzh/.

## References

*   [1] Bain, A. Mind and Body the Theories of Their Relation by Alexander Bain. Henry S. King & Company, 1873.
*   [2] Bengio, Y. Learning deep architectures for ai. Foundations and trends® in Machine Learning 2, 1 (2009), 1–127.
*   [3] Bengio, Y., and Delalleau, O. Justifying and generalizing contrastive divergence. Neural computation 21, 6 (2009), 1601–1621.
*   [4] Caruana, R., and Niculescu-Mizil, A. An empirical comparison of supervised learning algorithms. In Proceedings of the 23rd international conference on Machine learning (2006), ACM, pp. 161–168.
*   [5] Castro, J. L., Mantas, C. J., and Benıtez, J. Neural networks with a continuous squashing function in the output are universal approximators. Neural Networks 13, 6 (2000), 561–563.
*   [6] Dahl, G. E., Sainath, T. N., and Hinton, G. E. Improving deep neural networks for lvcsr using rectified linear units and dropout. In Acoustics, Speech and Signal Processing (ICASSP), 2013 IEEE International Conference on (2013), IEEE, pp. 8609–8613.
*   [7] Delalleau, O., and Bengio, Y. Shallow vs. deep sum-product networks. In Advances in Neural Information Processing Systems (2011), pp. 666–674.
*   [8] Dietrich, E. Computationalism.
*   [9] Erhan, D., Bengio, Y., Courville, A., Manzagol, P.-A., Vincent, P., and Bengio, S. Why does unsupervised pre-training help deep learning? The Journal of Machine Learning Research 11 (2010), 625–660.
*   [10] Fodor, J. A., and Pylyshyn, Z. W. Connectionism and cognitive architecture: A critical analysis. Cognition 28, 1 (1988), 3–71.
*   [11] Friedman, J. H. On bias, variance, 0/1—loss, and the curse-of-dimensionality. Data mining and knowledge discovery 1, 1 (1997), 55–77.
*   [12] Funahashi, K.-i., and Nakamura, Y. Approximation of dynamical systems by continuous time recurrent neural networks. Neural networks 6, 6 (1993), 801–806.
*   [13] Gelfand, A. E., Hills, S. E., Racine-Poon, A., and Smith, A. F. Illustration of bayesian inference in normal data models using gibbs sampling. Journal of the American Statistical Association 85, 412 (1990), 972–985.
*   [14] Glorot, X., Bordes, A., and Bengio, Y. Deep sparse rectifier neural networks. In International Conference on Artificial Intelligence and Statistics (2011), pp. 315–323.
*   [15] Goodfellow, I. J., Warde-Farley, D., Mirza, M., Courville, A., and Bengio, Y. Maxout networks. arXiv preprint arXiv:1302.4389 (2013).
*   [16] Hale, J. K. Dynamical systems and stability. Journal of Mathematical Analysis and Applications 26, 1 (1969), 39–59.
*   [17] Hastad, J. Almost optimal lower bounds for small depth circuits. In Proceedings of the eighteenth annual ACM symposium on Theory of computing (1986), ACM, pp. 6–20.
*   [18] Hebb, D. O. The organization of behavior: A neuropsychological approach. John Wiley & Sons, 1949.
*   [19] Hinton, G. E., Dayan, P., Frey, B. J., and Neal, R. M. The” wake-sleep” algorithm for unsupervised neural networks. Science 268, 5214 (1995), 1158–1161.
*   [20] Hinton, G. E., Osindero, S., and Teh, Y.-W. A fast learning algorithm for deep belief nets. Neural computation 18, 7 (2006), 1527–1554.
*   [21] Hinton, G. E., Srivastava, N., Krizhevsky, A., Sutskever, I., and Salakhutdinov, R. R. Improving neural networks by preventing co-adaptation of feature detectors. arXiv preprint arXiv:1207.0580 (2012).
*   [22] Hochreiter, S. Untersuchungen zu dynamischen neuronalen netzen. Diploma, Technische Universität München (1991).
*   [23] Hochreiter, S., and Schmidhuber, J. Long short-term memory. Neural computation 9, 8 (1997), 1735–1780.
*   [24] Hopfield, J. J. Neural networks and physical systems with emergent collective computational abilities. Proceedings of the national academy of sciences 79, 8 (1982), 2554–2558.
*   [25] Hornik, K., Stinchcombe, M., and White, H. Multilayer feedforward networks are universal approximators. Neural networks 2, 5 (1989), 359–366.
*   [26] Kirkpatrick, S., Gelatt, C. D., Vecchi, M. P., et al. Optimization by simulated annealing. science 220, 4598 (1983), 671–680.
*   [27] Kohonen, T. The self-organizing map. Neurocomputing 21, 1 (1998), 1–6.
*   [28] Krizhevsky, A., Sutskever, I., and Hinton, G. E. Imagenet classification with deep convolutional neural networks. In Advances in neural information processing systems (2012), pp. 1097–1105.
*   [29] LeCun, Y., Bottou, L., Bengio, Y., and Haffner, P. Gradient-based learning applied to document recognition. Proceedings of the IEEE 86, 11 (1998), 2278–2324.
*   [30] Lee, H., Grosse, R., Ranganath, R., and Ng, A. Y. Convolutional deep belief networks for scalable unsupervised learning of hierarchical representations. In Proceedings of the 26th Annual International Conference on Machine Learning (2009), ACM, pp. 609–616.
*   [31] Liou, C.-Y., Cheng, W.-C., Liou, J.-W., and Liou, D.-R. Autoencoder for words. Neurocomputing 139 (2014), 84–96.
*   [32] Manabe, S., and WETIIERALD, R. T. Thermal equilibrium of the atmosphere with a given distribution of relative humidity.
*   [33] Meunier, D., Lambiotte, R., Fornito, A., Ersche, K. D., and Bullmore, E. T. Hierarchical modularity in human brain functional networks. Frontiers in neuroinformatics 3 (2009).
*   [34] Mitchell, T. M. Machine learning. wcb, 1997.
*   [35] Nguyen, A., Yosinski, J., and Clune, J. Deep neural networks are easily fooled: High confidence predictions for unrecognizable images. arXiv preprint arXiv:1412.1897 (2014).
*   [36] Oja, E. Simplified neuron model as a principal component analyzer. Journal of mathematical biology 15, 3 (1982), 267–273.
*   [37] Oja, E., and Karhunen, J. On stochastic approximation of the eigenvectors and eigenvalues of the expectation of a random matrix. Journal of mathematical analysis and applications 106, 1 (1985), 69–84.
*   [38] Orponen, P. Computational complexity of neural networks: a survey. Nordic Journal of Computing 1, 1 (1994), 94–110.
*   [39] Pascanu, R., Gulcehre, C., Cho, K., and Bengio, Y. How to construct deep recurrent neural networks. arXiv preprint arXiv:1312.6026 (2013).
*   [40] Person, K. On lines and planes of closest fit to system of points in space. philiosophical magazine, 2, 559-572, 1901.
*   [41] Rosenblatt, F. The perceptron: a probabilistic model for information storage and organization in the brain. Psychological review 65, 6 (1958), 386.
*   [42] Smolensky, P. Information processing in dynamical systems: Foundations of harmony theory.
*   [43] Szegedy, C., Zaremba, W., Sutskever, I., Bruna, J., Erhan, D., Goodfellow, I., and Fergus, R. Intriguing properties of neural networks. arXiv preprint arXiv:1312.6199 (2013).
*   [44] Waibel, A., Hanazawa, T., Hinton, G., Shikano, K., and Lang, K. J. Phoneme recognition using time-delay neural networks. Acoustics, Speech and Signal Processing, IEEE Transactions on 37, 3 (1989), 328–339.
*   [45] Wan, L., Zeiler, M., Zhang, S., Cun, Y. L., and Fergus, R. Regularization of neural networks using dropconnect. In Proceedings of the 30th International Conference on Machine Learning (ICML-13) (2013), pp. 1058–1066.
*   [46] Werbos, P. J. Backpropagation through time: what it does and how to do it. Proceedings of the IEEE 78, 10 (1990), 1550–1560.

