# mmap_ninja_dataframe

Here, you can find a full list of the things you can do with `mmap-ninja-dataframe`.
A single sample is represented as a `dict`.
The two main abstractions are `DataFrameMmap` and `SparseDataFrameMmap`.
Use `DataFrameMmap` when you have the same keys present in every sample. 
If you have optional keys, which are available only in some samples, use `SparseDataFrameMmap`.

## Contents

DataFrameMmap API:

1. [Create a DataFrameMmap from a list of dictionaries](#create-a-dataframemmap-from-a-list-of-dictionaries)
2. [Create a DataFrameMmap from a dictionary of lists](#create-a-numpy-memmap-from-a-generator)
3. [Create a DataFrameMmap from a generator](#open-an-existing-numpy-memmap)
4. [Open an existing DataFrameMmap](#acces)
5. [Append new samples to a DataFrameMmap](#append-new-samples-to-a-numpy-memmap)

SparseDataFrameMmap API:

1. [Create a SparseDataFrameMmap from list of dictionaries](#create-a-raggedmmap-from-list-of-samples)
2. [Create a RaggedMmap from a generator](#create-a-raggedmmap-from-a-generator)
3. [Open an existing RaggedMmap](#open-an-existing-raggedmmap)
4. [Append new samples to a RaggedMmap](#append-new-samples-to-a-raggedmmap)


### Create a DataFrameMmap from a list of dictionaries

To create a `DataFrameMmap` from a `list` of `dict`s, just use the `DataFrameMmap.from_list_of_dicts` method:

```python
import numpy as np
from mmap_ninja_dataframe.dense import DataFrameMmap

dicts = [
    {'input': np.array([1., 3., 7.1]), 'target': 0},
    {'input': np.array([0.1, 23.]), 'target': 1}
]
DataFrameMmap.from_list_of_dicts(
    out_dir='dataframe',
    dicts=dicts,
    mode='sample',
    verbose=True
)
```

### Create a DataFrameMmap from a dictionary of lists
