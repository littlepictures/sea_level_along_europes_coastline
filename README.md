# CLIP - local sea level anomaly <img style="float: right;" src="https://raw.githubusercontent.com/trevalabs/.github/main/logos/trevelabs_logo.png" width="180">
<hr>

## TrevaLabs
 
[TrevaLabs](https://www.TrevaLabs.com) is a collective of climate data visualisation creatives in Europe, brought together by the desire to make a big impact with little pictures. Its mission is to rapidly create little pictures of climate for maximal human impact, and the vision is to reach every European by the end of decade with a little picture on Climate.


## Background on this CLIP
Sea level rise has a localized character and can vary greatly in different parts of Europe. For example, the North Sea region is particularly vulnerable due to land subsidence and increased storminess, while the Mediterranean is more affected by changes in ocean currents and salinity. To understand these differences, scientists use data derived from radar satellites to measure the height of the sea surface with millimeter precision.

This information is crucial for developing effective adaptation strategies, such as building sea defenses or planning for relocation of coastal populations.

## Data Sources

The CLIP uses the following datasets:
- Cazenave Anny, Gouzenes Yvan, Birol Florence, Legér Fabien, Passaro Marcello, Calafat Francisco M, Shaw Andrew, Niño Fernando, Legeais Jean François, Oelsmann Julius, Benveniste Jérôme (2022). New network of virtual altimetry stations for measuring sea level along the world coastlines. SEANOE. https://doi.org/10.17882/74354


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
