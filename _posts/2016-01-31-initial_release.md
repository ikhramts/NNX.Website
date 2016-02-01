---
layout: post
title: "Initial release"
author: "Iouri Khramtsov"
comments: false
---

NNX has now became a minimal viable product (and very minimal at that indeed), so off it goes into the world!

There's still lots of stuff to do. At the present, NNX supports the following:

* Multilayer perceptrons where each node in layer N is connected to each node in layer N+1.
* Activation function: \\(\tanh\\) for hidden layers, [softmax](https://en.wikipedia.org/wiki/Softmax_function) for output layer.
* Backpropagation: assumes [cross-entropy error](https://en.wikipedia.org/wiki/Cross_entropy).
* Backpropagation stopping conditions: either fixed number of epochs, or stop when error on validation set
  does not improve with an upper limit on epochs.

In near to medium future I am hoping to add:

* Regression neural networks, with output layers having tanh activation function instead of softmax.
* Composite networks that allow more structured connections between layers.
* Detailed training results: elapsed time, batch error at every epoch, etc.
* Faster training. There are some clear optimization oportunities.

Other things under consideration: replace most object creation methods with with a single
`nnMakeObject(...)` function. This will require some careful thinking about validation and
.NET API.

At the present I will likely focus only on feed-forward neural networks, as more complex
networks will likely be too heavy for Excel.
