---
layout: "function-reference"
title: "nnMakeArray"
---

## Inputs/outputs

Input arguments:

1. **Name**: string, not empty. Name of the array object to create.

2. **Values**: vertical or horizontal array of values. Must be one-dimensional; two-dimentional matricies will result in error. Values can be numbers (doubles), or strings.  All values must be of the same type: e.g. if the first value in the array is a number, then the rest must be numbers too.

**Returns**: name of the newly created array object.

## Remarks

Arrays created using `nnMakeArray()` are an intermediate step in creating weights using [`nnMakeWeights()`](nnMakeWeights.html).  See Sheet 2 on the [sample workbook](https://github.com/ikhramts/NNX/blob/master/Samples/Iris-flower-data-set.xlsx?raw=true) for an example.