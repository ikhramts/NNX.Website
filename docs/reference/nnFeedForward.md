---
layout: "function-reference"
title: "nnFeedForward"
---

For calculation details, see reference page for the neural network being used, e.g. [Multilayer perceptron](MultilayerPerceptron.html).

The output array may automatically expand over cells that are in use, so make sure to leave enough empty cells to the right of the cell containing the formula.

## Inputs/outputs

| Arguments   | | |
|-|:-:|---|
| `Name`  | string, not empty  | Name of the neural network to use.  |
| `Inputs` | array of numbers | Vertical or horizontal array of values to use as input in feeding forward. Number of elements must match the number of input nodes of the neural network. |

| Returns   |
|-----------|
| Auto-expanding horizontal array of numbers. |


