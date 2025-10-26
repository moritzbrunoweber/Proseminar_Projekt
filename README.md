# Proseminar_Projekt

## Sumary
The GRACE/GRACE-FO satellites, maintained by GravIS, monitor gravitational changes over the entire planet. GravIS provides information about terrestrial water storage anomalies (GravIS TWS Level-3 products), which display water mass anomalies expressed in terms of equivalent water height from all water storage compartments including snow, surface water, soil moisture, and deep groundwater relative to the long term mean period 2002/04 through 2020/03. I want to see, if these changes relate to areas of deforestation in the Amazon rain forest.

## Background and motivation
The Amazon rain forest plays a vital role in the earth's climate system and global water cycle. It acts as a big carbon sink and contributes significantly to regional and global precipitation patterns through evapotranspiration. However, widespread deforestation driven by agriculture, logging, and urbanization threatens the Amazon rain forest. Changes in forest cover can disrupt water storage and availability, affecting surface water, soil moisture, and groundwater dynamics. By analyzing terrestrial water storage anomalies from GRACE/GRACE-FO data in relation to deforestation areas, I want to see the impact deforestation has on the terrestrial water storage, which helps understanding the difficulties we will need to overcome.

## Objective
The result of my project will be a overview of an area in the Amazon rain forest which was subject to deforestation and relate that deforestation to measured changes in terrestrial water storage.

## Implementation
I want to first make out a suitable area for my project by looking at mapped deforestation and afterwards obtain the GRACE/GRACE-FO data from GravIS and tree cover data from MODIS. I will need to mask the chosen area and to align the spatial resolution of the data prior to creating two graphics, displaying the change in tree cover and terrestrial water storage. As a final result I want to relate those two maps to each other in order to visualize the effect deforestation has on the terrestrial water storage. The analysis will be made for two temporal windows: March 2002 - March 2003 and March 2024 - March 2025.

## Responsibilities and timeline
I want to have chosen a suitable area and obtained the raw data by session 8, manipulated the data by session 10 and by session 12 be finished with my graphics and report.

## Risks and contingency
I expect especially the MODIS tree cover data to be quite large, which is why I will choose a suitably big area for my project. The finding of said area will likely not be very easy, but I will burn that bridge when i get to it. As I have little to no experience with spatial data in R, I suspect this to also challenge me quite a bit. I have prepared a little by going through the brief introduction to working with geospatial data in R last week and will continue to learn and inform myself, to master this task successfully.

## Data
GRACE-FO TWS download: 
Boergens, E., Dobslaw, H., Dill, R. (2025):
  COST-G GravIS RL02 Terrestrial Water Storage Anomalies.
  V. 0001. GFZ Data Services. https://doi.org/10.5880/COST-G.GRAVIS_02_L3_TWS

MODIS tree cover download:
https://doi.org/10.5067/MODIS/MOD44B.061

Both data sets are well above 100 MB, therefore they are not included in the repository and must be downloaded manually. In my project, they will be accessed by this path: "C:\Users\Moritz.weber\Desktop\lokale Dateien\Uni\HS2025\Proseminar_Applied_Geodata_Science\data_external"

The GRACE-FO data has a monthly temporal resolution, ranging from April 2002 to the present. It is a global data set, so the area of interest will have to be cut out in later data processing.

The MODIS data is a yearly average from March 2003 - March 2004 and from March 2024 - March 2025.The area of interest is as follows:

Corner Coordinates:

Upper Left  ( -59.9329288,   0.0000000) ( 59d55'58.54"W,  0d 0' 0.01"N)

Lower Left  ( -59.9329288,  -9.9386031) ( 59d55'58.54"W,  9d56'18.97"S)

Upper Right ( -49.9441074,   0.0000000) ( 49d56'38.79"W,  0d 0' 0.01"N)

Lower Right ( -49.9441074,  -9.9386031) ( 49d56'38.79"W,  9d56'18.97"S)

The proper granules can also be found via the field "granule search", the two data sets to be downloaded are:

MOD44B.A2003065.h12v09.061.2022281001104
MOD44B.A2024065.h12v09.061.2025133155809