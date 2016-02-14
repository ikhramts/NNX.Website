---
layout: "function-reference"
title: "nnMakeSimpleGradientTrainer"
---

## Inputs/outputs


| Arguments   | | |
|-|:-:|---|
| `Name`  | string, not empty  | Name of the trainer object to create.  |
|  `NumEpochs` |  integer, &gt;0 | Number of backpropagation steps to perform during training. Each backpropagation step includes evaluating a batch of one or more training points.  |
| `LearningRate`  | number, &gt;0  | Used to determine the impact of gradient calculated in each backpropagation step on the neural network's weights.  |
| `Momentum`  | number, &geq;0  | Used to determine the impact of gradient calculated in _previous_ backpropagation step on the neural network's weights.  |
| `QuadraticRegularization`  | number, &geq;0  | Higher values force weights to stay closer to 0, hopefully preventing overfitting.  |
| `BatchSize`  | integer, &gt;0  | Number of training samples to include in every epoch.  |
| `Seed`  | integer, &geq;0  | Seed for random number generator.  Training runs with the same seed and same input parameters should always produce identical results.  |

| Returns   |
|-----------|
| Name of the newly created trainer object. |


## Details

Simple Gradient Trainer trains neural networks by applying `NumEpochs` backpropagation steps, calculating the gradient of the error function with respect to weights at every step and moving the weights in that direction, with some adjustments.

More specifically, for every backpropagation step \\(1 \leq t \leq \\) `NumEpochs`, the trainer selects `BatchSize` samples from the training set (at random, with replacement), and calculates the average of gradients of the network's error for each sample with respect to weights to arrive at the estimated overall gradient of network's error given its current weights, \\(\nabla E(\mathbf{w}_{t-1})\\).  The trainer then adds adjustments from `Momentum` (\\(m\\)) and `QuadraticRegularization` (\\(q\\)) to arrive at adjusted gradient \\(\nabla_t^\prime\\) to apply to the weights in this step:

\begin{equation}
\nabla_t^\prime = \nabla E(\mathbf{w}\_{t-1}) + m \nabla E(\mathbf{w}\_{t-2}) + q \mathbf{w}\_{t-1}
\end{equation}

The trainer then uses the adjusted gradient to calculate the new estimate for weights:

\begin{equation}
\mathbf{w}_t = \mathbf{w}\_{t-1} - \mathrm{LearningRate} \cdot \nabla_t^\prime
\end{equation}

These weights are then assigned to the neural network for use in the next backpropagation step.

### Meaning of learning rate, momentum, quadratic regularization

In formula (1) above, `Momentum` (\\(m\\)) term may help lessen effect of oscillations across a valley by adding previous step's gradient to this step's gradient,  though high momentums will lead to slower convergence.  

The `QuadraticRegularization` (\\(q\\)) term forces the gradient to point increasingly toward zero as the weights become bigger, thus preventing the weights from becoming too large or too small.  This lowers risk of overfitting, and ensures that the weights remain in the range where they are sensitive enough to corrections in future steps.

In formula (2), `LearningRate` determines the overall impact of the adjustment in each step, with higher values leading to higher adjustments, but also possibly leading to overshooting the optimum weights.

### Role of the neural network

The formulas above have purposefully omitted details on how to calculate the neural network's error gradient, \\(\nabla E(\mathbf{w}_{t-1})\\).  Like any other trainer in NNX, Simple Gradient Trainer is a generic trainer that can act on any neural network supported by NNX; the specifics of calculating the gradient are therefore provided by the neural network that the trainer acts on. These details can be found on reference page for the neural network, e.g. [Multilayer perceptron](MultilayerPerceptron.html).