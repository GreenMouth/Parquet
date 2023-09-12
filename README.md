# Parquet
File compression for large data files

Dataset:
https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page

Terminal:
(base) ~ % pwd
(base) ~ % cd /Users/Prashant.Shinde/Desktop
(base) Desktop % cd Parquet
(base) Parquet % pip install parquet-cli
(base) Parquet % parq trips.parquet --schema 
(base) Parquet % parq trips.parquet.parquet --head 5 
(base) Parquet % python
>>> import pyarrow.parquet as pq
>>> file = pq.ParquetFile("/Users/Prashant.Shinde/Desktop/Parquet/trips.parquet")
>>> file.metadata
>>> file.schema
>>> df = file.read().to_pandas()
>>> df.to_csv("trips.csv")
>>> df.to_json("trips.json", orient="records", lines=True)
>>> df.to_csv(‘trips.zip', compression={'method': 'zip', 'archive_name': ‘trips.csv'})
