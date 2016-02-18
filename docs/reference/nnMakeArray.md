---
layout: "function-reference"
title: "nnMakeArray"
---

Creates an array object. Arrays created using `nnMakeArray()` are an intermediate step in creating weights using [`nnMakeWeights()`](nnMakeWeights.html).  See Sheet 2 on the [sample workbook](https://github.com/ikhramts/NNX/blob/master/Samples/Iris-flower-data-set.xlsx?raw=true) for an example.

`Values` argument may contain blank cells; these cells will be skipped when creating an array. A blank cell is a cell with no value or an empty string (e.g. a cell containing formula `=""`). Cells containing errors or zeros do not count as empty cells.

## Inputs/outputs

| Arguments   | | |
|-|:-:|---|
| `Name`  | string, not empty  | Name of the array object to create.  |
| `Values` | array | Vertical or horizontal array of values. Must be one-dimensional; two-dimentional matricies will result in error. Values can be numbers (doubles), or strings.  All values must be of the same type; e.g. if the first value in the array is a number, then the rest must be numbers too.  Any blank cells will be skipped. |

| Returns   |
|-----------|
| Name of the newly created array object. |

