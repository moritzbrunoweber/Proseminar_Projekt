# Proseminar_Projekt

## Sumary
This project contains a reproducible code ("analysis/data_processing.R") which works with external data that needs to be downloaded manually and linked within the code, as explained in the subsection "Data". After the code has been run, the R-markdown ("vignettes/Projekt.Rmd") can be executed via the knit-function to obtain a finished HTML report.

The GRACE/GRACE-FO satellites, maintained by GravIS, monitor gravitational changes over the entire planet. GravIS provides information about terrestrial water storage anomalies (GravIS TWS Level-3 products), which display water mass anomalies expressed in terms of equivalent water height from all water storage compartments including snow, surface water, soil moisture, and deep groundwater relative to the long term mean period 2002/04 through 2020/03. I want to see, if these changes relate to areas of deforestation in the Amazon rain forest.

## Background and motivation
The Amazon rain forest plays a vital role in the earth's climate system and global water cycle. It acts as a big carbon sink and contributes significantly to regional and global precipitation patterns through evapotranspiration. However, widespread deforestation driven by agriculture, logging, and urbanization threaten the Amazon rain forest. Changes in forest cover can disrupt water storage and availability, affecting surface water, soil moisture, and groundwater dynamics. By analyzing terrestrial water storage anomalies from GRACE/GRACE-FO data in relation to deforestation areas, I want to see the impact deforestation has on the terrestrial water storage, which helps understanding the difficulties we will need to overcome. 

## Objective
The result of my project will be a overview of the Amazon rain forest, which will depict the change of tree cover due to deforestation. I will relate this change to the change in the yearly amplitude of terrestrial ground water storage for the same area to see a possible correlation between the two. 

## Implementation
I will acquire the tree cover data from MODIS and the TWS data from GravIS. The MODIS tree cover data will need to be mosaiced together to cover my area of interest and the GravIS TWS data will need to be masked by the area of interest. Furthermore, I will need to align the saptial resolution of the two data sets, as the MODIS tree cover data has a spatial resolution of 250 meters and the GravIS TWS data of about 300 kilometers. I will estimate he change of tree cover by comparing the earliest and latest available data (March 2000 - March 2001 and March 2024 - March 2025) and relating the change in tree cover to the linear regression made with the time series of the yearly TWS amplitude, ranging from the earliest to the latest available data (April 2002 - May 2025).

## Addendum
To make sure I can work with the two data sets, I already acquired and manipulated all of the data I will need (GravIS TWS data and MODIS tree cover data for both periods). I masked down the GravIS TWS data to my area of interest and I mosaiced the MODIS tree cover data for both time periods and also masked them down to the area of interest. The data sets are too large to upload to my git repository, therefore the data needs to be downloaded as described and the script ran locally in order to look at the results. Alternatively, it can be looked at on my device.

## Responsibilities and timeline
I want to have chosen a suitable area and obtained the raw data by session 8, manipulated the data by session 10 and by session 12 be finished with my graphics and report.

## Risks and contingency
I expect especially the MODIS tree cover data to be quite large, which is why I will choose a suitably big area for my project. As I have little to no experience with spatial data in R, I suspect this to also challenge me quite a bit. I have prepared a little by going through the brief introduction to working with geospatial data in R last week and will continue to learn and inform myself, to master this task successfully.

## Data
GRACE-FO TWS download: 
Boergens, E., Dobslaw, H., Dill, R. (2025):
  COST-G GravIS RL02 Terrestrial Water Storage Anomalies.
  V. 0001. GFZ Data Services. https://doi.org/10.5880/COST-G.GRAVIS_02_L3_TWS

MODIS tree cover download:
https://doi.org/10.5067/MODIS/MOD44B.061

Both data sets are well above 100 MB, therefore they are not included in the repository and must be downloaded manually. In my project, they will be accessed via local paths which will need to be replaced only at the very beginning of the code, located in the file "analysis/data_processing.R".

The GRACE-FO data has a monthly temporal resolution, ranging from April 2002 to the present. It is a global data set, so the area of interest will have to be cut out in later data processing.

The MODIS data is a yearly average from March 2000 - March 2001 and from March 2024 - March 2025.The area of interest is as follows:

Corner Coordinates:

Upper Left  (-77.0000000,  6.0000000)

Lower Left  (-77.0000000, -18.0000000)

Upper Right (-48.0000000,  6.0000000)

Lower Right ( -48.0000000, -18.0000000)

The proper granules can be found by inputting these coordinates in the spatial filter, which will result in 12 granules for each of the time periods.
