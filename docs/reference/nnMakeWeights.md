---
layout: "function-reference"
title: "nnMakeWeights"
---

Creates a weights object from arrays created using [`nnMakeArray()`](nnMakeArray.html). 

## Inputs/outputs

| Arguments   | | |
|-|:-:|---|
| `Name`  | string, not empty  | Name of the Weights object to create.  |
| `WeightArrays` | array of strings | Vertical or horizontal array of references to arrays created using [`nnMakeArray()`](nnMakeArray.html), each array representing a layer of connections the neural network. Number of values in each array must match the expected number of weights in corresponding layer. For layout of weights in each layer, see reference page for the relevant neural network, e.g. [Multilayer perceptron](MultilayerPerceptron.html).|

| Returns   |
|-----------|
| Name of the newly created Weights object. |

