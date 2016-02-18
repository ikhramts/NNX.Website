---
layout: "function-reference"
title: "nnGetCrossEntropyError"
---

Cross-entropy error between expected target values \\(\mathbf{t} = (t_1, ..., t_n)\\) and observed outputs \\(\mathbf{o} = (o_1, ..., o_n)\\) is given by 

\begin{equation}
CE(\mathbf{t}, \mathbf{o}) = -\sum_{i=1}^{n} t_i \ln o_i
\end{equation}


## Inputs/outputs

| Arguments   | | |
|-|:-:|---|
| `Expected`  | array of numbers  | Array of values that were expected to be produced by the neural network.  |
| `Actual` | array of numbers | Array of values that were actually produced by the neural network. Must be the same size as `Expected` array. |

| Returns   |
|-----------|
| Number; cross entropy error of the neural network's output for this observation. |


