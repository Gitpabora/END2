### What is a neural network neuron?

The concept of neurone  inneural network was eastablished in 1940s by Warren McCulloch and Walter Pitts. The concept was inspired from brain neuron which is the basic element of brain.Brain neuron store , carry and transmit messages from one neuron to other using electrical impulse and chemical signals.This conceptual neuron can be thought of as comprising of small memory or  potential signal and there is activation resulted out of the neuron based on certain inputs along with associated weights.
Mathematically, if there are n inputs(xi) to a neuron, Wi s are the weights an example activation is  z=tanh(Sum( Xi* Wi+ b)for all i ) where b is a bias
Many functions(e.g relu, sigmoid etc) were establised to use for an activation similar to tanh function used in this example. 
The neurons can be interconnected in layers to build a neural network. 




### What is the use of the learning rate?

Learning rate (lr) istermed a hyper parameter to control how much adjusting to the model weights w.r.t model gradient are done.
If the rate is more , more adjustments are done , a trade off is needed depending on the problem so that  the calculations does not get stuck at minima
Empirically an option used is to vary the learning rate as the training progresses ,progressively reducing lr.
Various mathematical functions can also be experimented for controlling the leraning rate prgramaatically.



### How are weights initialized?

Weights were initialized heuristically, in random values. 
This can be random because While using specific optimization alogorithms at every step the weights are adjusted for arriving an optimum solution of minimized loss



#### Weight initialization fro Sigmoid and tanh

 [ ref :https://machinelearningmastery.com/weight-initialization-for-deep-learning-neural-networks/ ]

A method xavier initialization method is used for this purpose is that it calculates random number with a uniform probability distribution (U) between the range -(1/sqrt(n)) and 1/sqrt(n),where n is the number of inputs to the node.
 weight = U [-(1/sqrt(n)), 1/sqrt(n)]

Another method -normalized xavier initialization calculate a random number with a uniform probability distribution (U) between the range -(sqrt(6)/sqrt(n + m)) and sqrt(6)/sqrt(n + m), where n is the number of inputs to the node (e.g. number of nodes in the previous layer) and m is the number of outputs from the layer (e.g. number of nodes in the current layer).
weight = U [-(sqrt(6)/sqrt(n + m)), sqrt(6)/sqrt(n + m)]


### What is "loss" in a neural network?

Loss is the difference of predicted output from the actual output, training a neural network is an optimization problem of arriving at a state of the network(weights or parameters ) where the loss is minimum.

Various mathematical functions are used to calculate loss.e,g.
-Mean square error ( overcoming the negative deviations)
-Smooth L1 Loss (preventing exploding gradient by taking absolute error when absolute difference  is > 1) , 
-Cross entropy loss(greater penalty when incorrect predictions are made with higher confidence)



### What is the "chain rule" in gradient flow?

A neural netwok consists of layers. From the input layer the activations goes forward till the last layer for the objective function cost or loss. 
Backpropagation method is used  to minimize the objective function by adjusting the weights. The adjustments are determined by the gradients of the cost function with respect to the weights.
The matthematical basis for Back propagation is established by using the Chain rule for partial derivative.
The partial derivative of Loss function w.r.t the weights is equal to the multiplication of the partial derivatiove of Loss function w.r.t. Activation AND partial derivatiove Activation w.r.t weight

(ref : https://towardsdatascience.com/understanding-backpropagation-algorithm-7bb3aa2f95fd)
