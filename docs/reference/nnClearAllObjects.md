---
layout: "function-reference"
title: "nnClearAllObjects"
---

Deletes all named objects from NNX internal object store.  Any references to previously created objects will become invalid and will result in errors.

After using this function, make sure to delete it from the cell containing it so any further recalculations would not result in re-deleting any newly made objects.

## Inputs/outputs

| Arguments   |
|-|
| None. |

| Returns   |
|-----------|
| String "OK". |


