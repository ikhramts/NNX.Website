---
layout: "function-reference"
title: "nnMakeMultilayerPerceptron"
---

Directly creates a [multilayer perceptron](MultilayerPerceptron.html) that is ready to use in calculations. See documentation for [multilayer perceptron](MultilayerPerceptron.html) for more details.

## Inputs/outputs

| Arguments   | | |
|-|:-:|---|
| `Name`  | string, not empty  | Name of the multilayer perceptron object to create.  |
| `NumInputs`  | integer, &gt; 0  | Number of input nodes, not including input bias.  |
| `NumOutputs`  | integer, &gt; 0  | Number of output nodes.  |
| `HiddenLayerSizes`  | array of integers  | Number of nodes in each hidden layer, not including biases. Each element must be greater than zero.  |
| `Weights`  | string, not empty  | Name of the weights object created using [`nnMakeWeights()`](nnMakeWeights.html).  |

| Returns   |
|-----------|
| Name of the newly created neural network object. |

