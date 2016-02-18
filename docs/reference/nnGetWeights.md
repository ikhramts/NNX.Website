---
layout: "function-reference"
title: "nnGetWeights"
---

Returns weights for connections leading to the specified layer in the neural network.  For details on the layout of weights in the returned array see reference page for the neural network being used, e.g. [Multilayer perceptron](MultilayerPerceptron.html).

The output array may automatically expand over cells that are in use, so make sure to leave enough empty cells below the cell containing the formula.

## Inputs/outputs

| Arguments   | | |
|-|:-:|---|
| `Name`  | string, not empty  | Name of the neural network to use.  |
| `Layer` | integer | Layer of the neural network for which to produce weights, with layer 1 layer being the layer of connections leading to the first set of hidden nodes. |

| Returns   |
|-----------|
| Auto-expanding vertical array of numbers. |


