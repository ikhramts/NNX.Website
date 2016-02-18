---
layout: "function-reference"
title: "nnTrainMultilayerPerceptron"
---

Creates and trains a [multilayer perceptron](MultilayerPerceptron.html) from the provided inputs.  Number of input and output nodes is inferred from the training set.  See documentation for [multilayer perceptron](MultilayerPerceptron.html) and the trainer being used for more details.

## Inputs/outputs

| Arguments   | | |
|-|:-:|---|
| `Name`  | string, not empty  | Name of the multilayer perceptron object to create.  |
| `TrainerName`  | string, not empty  | Name of the trainer object that will train this neural network.  |
| `Inputs`  | matrix  | Table of training inputs. Each row represents an observation.  |
| `Targets`  | matrix  | Table of training target values. Each row represents expected outcome for the corresponding row of training inputs. Must be the same height as `Inputs` matrix. |
| `HiddenLayerSizes`  | array of integers  | Number of nodes in each hidden layer, not including biases. Each element must be greater than zero.  |

| Returns   |
|-----------|
| Name of the newly created neural network object. |

