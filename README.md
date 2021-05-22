# About the Data

This project uses two main data sources. The first is the representative spending data, and the second is the shapefile that has been directly uploaded to Mapbox for performance reasons.

There is a CSV file in this repository (repspending.csv), which has been cleaned and processed, but comes from [ProPublica, and consists of the 2020 Representative Spending (Q1-Q4) files](https://projects.propublica.org/represent/expenditures).

The shapefile comes directly from [the US Census in their TIGER Shapefiles, found here as 2020 US Congressional Districts.](https://www.census.gov/cgi-bin/geo/shapefiles/index.php)

## Methodology

The CSV was heavily processed, due to the inherent dirtiness of the data, covered [here in ProPublica's warnings about the disbursement data.](https://www.propublica.org/article/update-on-house-disbursements-a-few-notes-on-how-to-use-the-data)

In order to get workable data, I removed all data that was not from 2020, manually coded and researched which representatives were part of the 116th Congress and which weren't, and generated GEOIDs for the representatives, which consisted of the FIPS code + the representative's district. Most of this data cleaning and processing was done using Python in a Jupyter Notebook (pandas and NumPy as essential packages), and QGIS (by using data joins, aggregate functions to sum up amounts, and matching up miscalculated GEOIDs due to the nature of how disbursements report district numbers).

QGIS was also essential for understanding the binning, which was done using JavaScript in the end for performativity (instead of loading 10 styles from Mapbox) and in the end, the data was binned into 5 classes to show clear delineations in the amounts as they were in QGIS.
