# Geographical Characterisation of British Urban Form and Function using the Spatial Signatures Framework - the underlying data

This repository contains the underlying data used to develop geographical characterisation of British urban form and function using the Spatial Signatures framework.

It contains three partitioned Apache Parquet files:

- `form`
    - Apache Parquet file containing enclosed tessellation geometry and all form-based characters, both invididual and contextualised. The file follows the specifications for storing geospatial data in Apache Arrow and Apache Parquet v0.1.0 (WKB).
- `function`
    - Apache Parquet file containing all function-based characters, both invididual and contextualised.
- `signature_type`
    - Apache Parquet file containing signature type of each cell.
    
All files share the `hindex` field allowing their combination.