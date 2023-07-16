## Neural Network

Much of the information given below is taken from the book "Neural Networks and Deep Learning" written by **Michael Nielsen**. Ref: http://neuralnetworksanddeeplearning.com/chap1.html

The idea is to recignize the following pattern automatically: 

<img src="https://github.com/victoriazinkovich/ML-Exercises/assets/78615928/edf1bceb-3ec3-4442-b8ba-f0932983eb63" width="150" />

$\text{}$

To recognize individual digits we will use a **three-layer neural network**:

<img src="https://github.com/victoriazinkovich/ML-Exercises/assets/78615928/842f5b9a-e726-4643-b474-c13eb8f8a7ea" width="350" />

1. The input layer of the network contains neurons encoding the values of the input pixels. The input pixels are greyscale, with a value of 0.0 representing white, a value of 1.0 representing black, and in between values representing gradually darkening shades of grey.
2. The second layer of the network is a hidden layer. We denote the number of neurons in this hidden layer by $n$, and we'll experiment with different values for $n$.
3. The output layer of the network contains 10 neurons (i.e. if the first neuron has an output $\approx$ 1, then that will indicate that the network thinks the digit is a 0).

$\text{}$

To quantify how well we are training the network we define a cost function (we minimize it instead of number of correctly guessed images sincethe cost function is *smooth*):

$C( \omega, b)  \equiv \dfrac{1}{2n} \sum_x \parallel y(x) - a \parallel $

So the aim of our training algorithm will be to minimize the cost $C(\omega,b)$ as a function of the weights and biases. In other words, we want to find a set of weights and biases which make the cost as small as possible. We'll do that using an algorithm known as **stochastic gradient descent**.

$\text{}$

## Stochastic Gradient Descent
Let's first examine the more simple idea of gradient descent. Based on the idea that we launch a ball in a valley, trying to find the minimum of the function $C(\upsilon_1, \upsilon_2)$.

$\Delta C \approx \dfrac{\partial C}{\partial \upsilon_1}\Delta \upsilon_1 + \dfrac{\partial C}{\partial \upsilon_2}\Delta \upsilon_2 \approx \nabla C \Delta \upsilon$

Then, the law of ball's motion can be defined as:

$\Delta \upsilon \approx -\eta \nabla С$

$\Delta C  \approx -\eta ||\nabla C||^2$ < 0  $\longrightarrow$  downward movement of the function

Finally,

$\upsilon \longrightarrow \upsilon^{'} = \upsilon -  \eta \nabla С$

In practical implementations, $\eta$ is often varied so that equation above remains a good approximation, but the algorithm isn't too slow.

$\text{}$

Since the cost function has the form of sum, we need to compute each gradient of the sum separately, that can take a long time. An idea called **stochastic gradient descent** can be used to speed up learning. The idea is to estimate the gradient $\nabla C$ by computing $\nabla C_x$ for a small sample of randomly chosen training inputs. Then we pick out another randomly chosen mini-batch and train with those. And so on, until we've exhausted the training inputs, which is said to complete an epoch of training. At that point we start over with a new training epoch.

$\text{}$

## Backpropagation algorithm
To find partial derivatives $\partial C/\partial \omega$ and $\partial C/\partial b$ of the cost function C with respect to any weight $\omega$ (or bias $b$) the backpropagation algorithm is used. First, we introduce the error function

$\delta^L_j = \dfrac{\partial C}{\partial z_j^l} = \dfrac{\partial C}{\partial a_j^l} \sigma'(z^L_j)$

By combining equations of error evolution we can compute the error for any layer in the network. 







