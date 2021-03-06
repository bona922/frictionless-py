# Working with Pandas

> Status: **EXPERIMENTAL**

Frictionless supports reading and writing Pandas dataframes.

```sh
! pip install frictionless[pandas]
```


## Reading from Pandas

You can read a Pandas dataframe:

```py
from frictionless import Package

package = Package.from_pandas(dataframes=['table1': '<df1>', 'tables2': '<df2>'])
print(package)
for resource in package.resources:
  print(resource.read_rows())
```


## Wriring to Pandas

> **[NOTE]** Timezone information is ignored for `datetime` and `time` types.

You can write a dataset to Pandas:

```py
from frictionless import Package

package = Package('path/to/datapackage.json')
dataframes = package.to_pandas()
```


## Configuring Pandas

There are no options available in `PandasDialect`.

References:
- [Pandas Dialect](https://frictionlessdata.io/tooling/python/dialects-reference/#pandas)