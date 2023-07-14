Much of the information given below is taken from the book "Neural Networks and Deep Learning" written by **Michael Nielsen**. Ref: http://neuralnetworksanddeeplearning.com/chap1.html

The idea is to recignize the following pattern automatically: 

<img src="https://github.com/victoriazinkovich/ML-Exercises/assets/78615928/edf1bceb-3ec3-4442-b8ba-f0932983eb63" width="150" />

To recognize individual digits we will use a **three-layer neural network**:

<img src="https://github.com/victoriazinkovich/ML-Exercises/assets/78615928/842f5b9a-e726-4643-b474-c13eb8f8a7ea" width="350" />

1. The input layer of the network contains neurons encoding the values of the input pixels. The input pixels are greyscale, with a value of 0.0 representing white, a value of 1.0 representing black, and in between values representing gradually darkening shades of grey.
2. The second layer of the network is a hidden layer. We denote the number of neurons in this hidden layer by $n$, and we'll experiment with different values for $n$.
3. The output layer of the network contains 10 neurons (i.e. if the first neuron has an output $\approx$ 1, then that will indicate that the network thinks the digit is a 0).

To quantify how well we are training the network we define a cost function:

<img src="https://latex.codecogs.com/svg.latex?\Large&space;x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}" title="\Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}" />
