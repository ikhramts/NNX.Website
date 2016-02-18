---
layout: "function-reference"
title: "nnMakeUntilDoneGradientTrainer"
---

`UntilDoneGradientTrainer` works similarly to [`SimpleGradientTrainer`](nnMakeSimpleGradientTrainer.html), except it splits the provided training set into a training and validation portion in proportion to `ValidationSetFraction` argument. During training, the trainer checks periodically whether the overall error on the validation set has improved, and if it has not improved after a certain number of epochs, it aborts training and sets the final neural network weights to the value that produced the best result so far.

This approach is designed to lower chance of overfitting compared to `SimpleGradientTrainer`, though as a tradeoff it reduces the total number of samples available for training.

## Inputs/outputs

| Arguments   | | |
|-|:-:|---|
| `Name`  | string, not empty  | Name of the trainer object to create.  |
| `NumEpochs`  | integer, &gt;0  | Maximum number of backpropagation steps to perform during training. Each backpropagation step includes evaluating a batch of one or more training points.  |
| `LearningRate`  | number, &gt;0  | Used to determine the impact of gradient calculated in each backpropagation step on the neural network's weights.  |
| `Momentum`  | number, &geq;0  | Used to determine the impact of gradient calculated in previous backpropagation step on the neural network's weights.  |
| `QuadraticRegularization`  | number, &geq;0  | Higher values force weights to stay closer to 0, hopefully preventing overfitting.  |
| `BatchSize`  | integer, &gt;0  | Number of training samples to include in every epoch.  |
| `ValidationSetFraction`  | number, strictly between 0 and 1  | Portion of the training set to use as validation set to check whether training has improved performance of the neural network.  |
| `MaxEpochsWithoutImprovement`  | integer, &gt;0  | Training will abort after there is no error improvement on validation set after this number of backpropagation steps.  |
| `EpochsBetweenValidations`  | number, &gt;0  | Number of backpropagation steps to perform between checking for error improvement on validation set.  |
| `Seed`  | integer, &geq;0  | Seed for random number generator. Training runs with the same seed and same input parameters should always produce identical results.  |

| Returns   |
|-----------|
| Name of the newly created trainer object. |

## Details

Given a training sample with \\(N\\) elements, before starting a training run, `UntilDoneGradientTrainer` selects `ValidationSetFraction`\\(\cdot N\\) samples to serve as validation set (randomly, without replacement).  These samples are removed from the training set and are not used for gradient calculations.  After that, the trainer proceeds with backpropagation algorithm as described in [`nnMakeSimpleGradientTrainer()`](nnMakeSimpleGradientTrainer.html), except every `EpochsBetweenValidations` epochs it calculates the total error on the validation set.  If the trainer does not observe improvement in error after `MaxEpochsWithoutImprovement` epochs, it aborts the training run.  If not, the trainer stops after `NumEpochs` epochs.

Regardless of how the trainer stopped, it selects the weights that have produced lowest error on the validation set so far as the final weights for the neural network.

