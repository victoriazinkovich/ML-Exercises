## Neural Network

Much of the information given below is taken from the book "Neural Networks and Deep Learning" written by **Michael Nielsen**. Ref: http://neuralnetworksanddeeplearning.com/chap1.html

The idea is to recignize the following pattern automatically: 

<img src="https://github.com/victoriazinkovich/ML-Exercises/assets/78615928/edf1bceb-3ec3-4442-b8ba-f0932983eb63" width="150" />

To recognize individual digits we will use a **three-layer neural network**:

<img src="https://github.com/victoriazinkovich/ML-Exercises/assets/78615928/842f5b9a-e726-4643-b474-c13eb8f8a7ea" width="350" />

1. The input layer of the network contains neurons encoding the values of the input pixels. The input pixels are greyscale, with a value of 0.0 representing white, a value of 1.0 representing black, and in between values representing gradually darkening shades of grey.
2. The second layer of the network is a hidden layer. We denote the number of neurons in this hidden layer by $n$, and we'll experiment with different values for $n$.
3. The output layer of the network contains 10 neurons (i.e. if the first neuron has an output $\approx$ 1, then that will indicate that the network thinks the digit is a 0).

$\text{}$

To quantify how well we are training the network we define a cost function (we minimize it instead of number of correctly guessed images sincethe cost function is *smooth*):

$C( \omega, b)  \equiv \dfrac{1}{2n} \sum_x \parallel y(x) - a \parallel $

So the aim of our training algorithm will be to minimize the cost $C(\omega,b)$ as a function of the weights and biases. In other words, we want to find a set of weights and biases which make the cost as small as possible. We'll do that using an algorithm known as **gradient descent**.

$\text{}$

## Gradient Descent








