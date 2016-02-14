---
layout: "function-reference"
title: "nnMakeSimpleGradientTrainer"
---

## Inputs/outputs

Input arguments:

| Argument  | Type  | Description  |
|:-:|:-:|---|
| Name  | string, not empty  | Name of the trainer object to create.  |
|  NumEpochs |  integer, &gt;0 | Number of backpropagation steps to perform during training. Each backpropagation step includes evaluating a batch of one or more training points.  |


1. **Name**: string, not empty.  
    Name of the trainer object to create.
    
2. **NumEpochs**: integer, &gt;0.  
    Number of backpropagation steps to perform during training. Each backpropagation step includes evaluating a batch of one or more training points.
    
3. **LearningRate**: number, &gt;0.  
    Used to determine the impact of gradient calculated in each backpropagation step on the neural network's weights.

4. **Momentum**: number, &geq;0.  
    Used to determine the impact of gradient calculated in _previous_ backpropagation step on the neural network's weights.

5. **QuadraticRegularization**: number, &geq;0.  
    Higher values force weights to stay closer to 0, hopefully preventing overfitting.

6. **BatchSize**: integer, &gt;0. 

7. **Seed**: integer, &geq;0.  
    Seed for random number generator.  Training runs with the same seed and same input parameters should always produce identical results.

**Returns**: name of the newly created trainer object.

## Details



