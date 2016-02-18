---
layout: "function-reference"
title: "nnGetMeanSquareError"
---

Mean square error between expected target values \\(\mathbf{t} = (t_1, ..., t_n)\\) and observed outputs \\(\mathbf{o} = (o_1, ..., o_n)\\) is given by 

\begin{equation}
ME(\mathbf{t}, \mathbf{o}) = \frac{1}{n}\sum_{i=1}^{n} (o_i - t_i)^2
\end{equation}


## Inputs/outputs

| Arguments   | | |
|-|:-:|---|
| `Expected`  | array of numbers  | Array of values that were expected to be produced by the neural network.  |
| `Actual` | array of numbers | Array of values that were actually produced by the neural network. Must be the same size as `Expected` array. |

| Returns   |
|-----------|
| Number; mean square error of the neural network's output for this observation. |

