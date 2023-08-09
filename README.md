# little picture - sea level along europe’s coastline

## Background on this little picture
_observing sea level trends where the impact if felt_

The impacts of rising sea levels are felt along the coast. Satellite data provide a key role in improving better estimation of coastal sea level trends across Europe ... and beyond! This illustration highlights data from &#39;virtual&#39; coastal sea level stations, using reprocessed satellite altimetry data around the europe’s coastline.

https://climate.esa.int/en/little-pictures-gallery/sea-level-along-Europes-coastline/

## Data Sources

The science data used for this Little Picture was sourced from the Sea Level CCI project of the European Space Agency (ESA) Climate Change Initiative (CCI) programme and will be made available on the CCI data facility soon. For other data products, key documents, publications and further information visit CCI Sea Level.

A corresponding sea level data record is provided operationally by the ECMWF Copernicus Climate Change Service.

Data from EUMETSAT operated missions contribute to climate monitoring.

## Data Preparation

This CLIP can easily be reproduced using the code in the python jupiter notebook provided in the "scripts" folder. The code automatically downloads and preprocessed the data into a csv file meant to be used in datawrapper or similar visualization tools. 

The code defines a function called "nc2csv" that extracts data from a file with the ".nc" file extension and converts it into a Pandas dataframe. The function takes in four arguments: "infile," which is the input file; "year," which is the year for which data should be extracted; "month," which is the month for which data should be extracted; and "list_viz," which is a list that the extracted data will be appended to. The function first opens the input file using the xarray library, adds year and month columns to the data set, and converts it to a dataframe. It then filters the dataframe to only include rows for the specified year and month, and keeps only certain columns (latitude, longitude, and "local_sla_trend"). It then aggregates the submeasurements by taking the mean, converts the resulting dataframe to a list, and appends it to the "list_viz" list which is the saved as a .csv file.

To prepare the data, follow these steps:

 - Run the notebook "clip_6_sea_level_rise_locally_dataprep.ipynb" and wait for the data download and preprocessing. Depending on the available internet connection it should be finished in ±2 minutes.
 - Optional: Adapt the bounding box (latitude and longitude filter) for your area of interest and rerun notebook

## Creating Visualizations
This example uses DataWrapper, but similar visualizations can also be created using other tools. To create a new visualization, follow these steps:

 - Log into Datawrapper and create a new symbol map or new scatter plot
 - Upload .csv file created by jupyter notebook 
 - Datawrapper should automatically parse latitude and longitude columns and create a symbol per measurement
 - Change symbols to your liking and use "sla" column for height and color

## CREDITS & LICENSE
- Idea by: [SEANOE](https://doi.org/10.17882/74354)
- Processing Scripts by: [UBILABS](https://www.ubilabs.com/)
- Visualization by: [UBILABS](https://www.ubilabs.com/)

The code in this repository is published under [CC BY-SA 4.0 license](https://creativecommons.org/licenses/by-sa/4.0/)
