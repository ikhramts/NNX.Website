---
layout: "function-reference"
title: "nnGetWeights"
---

## Inputs/outputs

| Arguments   | | |
|-|:-:|---|
| `Name`  | string, not empty  | Name of the neural network to use.  |
| `Layer` | integer | Layer of the neural network for which to produce weights, with layer 1 being the first hidden layer. |

| Returns   |
|-----------|
| Auto-expanding vertical array of numbers. |

## Remarks

For details on the layout of weights in the returned array see reference page for the neural network being used, e.g. [Multilayer perceptron](MultilayerPerceptron.html).

The output array may automatically expand over cells that are in use, so make sure to leave enough empty cells below the cell containing the formula.