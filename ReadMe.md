# Geographical Characterisation of British Urban Form and Function using the Spatial Signatures Framework - the underlying data

This repository contains the underlying data used to develop geographical characterisation of British urban form and function using the Spatial Signatures framework.

This is a data annexe to the Open Data Product available at https://doi.org/10.6084/m9.figshare.16691575.v1. More background on the notion of Spatial Signatures available in https://doi.org/10.1016/j.habitatint.2022.102641

## Content

The repository contains three partitioned Apache Parquet files:

- `form`
    - Apache Parquet file containing enclosed tessellation geometry and all form-based characters, both invididual and contextualised. The file follows the specifications for storing geospatial data in Apache Arrow and Apache Parquet v0.1.0 (WKB).
- `function`
    - Apache Parquet file containing all function-based characters, both invididual and contextualised.
- `signature_type`
    - Apache Parquet file containing signature type of each cell.
    
All files share the `hindex` field allowing their combination.

## Use

The recommended way of use is by loading the dataset as a [`dask_geopandas.GeoDataFrame`](https://dask-geopandas.readthedocs.io/en/stable/docs/reference/geodataframe.html) object. To connect to the data:

1. Clone the repository:

```shell
> git clone https://github.com/urbangrammarai/signatures_gb.git
```

2. Fire up a Python session on an environment where [`dask-geopandas`](https://dask-geopandas.readthedocs.io/en/stable/index.html) is installed (for example, the ['gds_env'](https://darribas.org/gds_env/)), and import it to the session:

```python
import dask_geopandas
```

3. Connect to the required table (e.g., form):

```python
db = dask_geopandas.read_parquet('form')
```

4. The above should give you access to the table:

```python
>>> db.info()
<class 'dask_geopandas.core.GeoDataFrame'>
Columns: 238 entries, hindex to area-weighted ETCs of enclosure (Q3)
dtypes: geometry(1), object(1), float64(234), int64(2)

>>>  db.head()
             hindex  ... area-weighted ETCs of enclosure (Q3)
0  c000e109777t0000  ...                             0.001069
1  c000e109777t0001  ...                             0.001024
2  c000e109777t0002  ...                             0.001024
3  c000e109777t0003  ...                             0.001064
4  c000e109777t0004  ...                             0.000928

[5 rows x 238 columns]
```

## Column names and descriptions

[Work in progress]

Column names and descriptions are available from:

- The two dictionaries in [here](https://urbangrammarai.xyz/spatial_signatures/data_product/create_data_product.html#rename-columns)
- The official but aggregated description on [Figshare](https://figshare.com/articles/dataset/Geographical_Characterisation_of_British_Urban_Form_and_Function_using_the_Spatial_Signatures_Framework/16691575?file=30904888)
