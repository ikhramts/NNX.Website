---
layout: "function-reference"
title: "nnMakeWeights"
---

## Inputs/outputs

| Arguments   | | |
|-|:-:|---|
| `Name`  | string, not empty  | Name of the Weights object to create.  |
| `WeightArrays` | array of strings | Vertical or horizontal array of references to arrays created using [`nnMakeArray()`](nnMakeArray.html), each array representing a layer of the neural network. |

| Returns   |
|-----------|
| Name of the newly created Weights object. |

## Remarks

Number of values in each .