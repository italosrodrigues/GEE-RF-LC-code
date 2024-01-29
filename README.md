# GEE-RF-code
The code used for the Randon Forest (RF) model in Google Earth Engine (GEE) 

For Land Sat 5: RF_LS5

For Land Sat 8: RF_LS8

This model was used by Italo Rodrigues as part of his PhD project "Multi-decadal Floodplain Classification and Trend Analysis in the Upper Columbia River Valley, British Columbia" as a first approach for land cover classification.

The model inputs are divided in to files:

Training pixels data (70% used for training)

Validation pixels data (30% reserved for training)

In this research, we utilise a variety of reference remote sensing data sources: UAV and Airborne LiDAR, aerial photographs, geotagged photos, Sentinel 2, and historical classified land cover (Hermosilla et al., 2022) to generate training samples per each year. 

To extract or determine the most reliable training pixels within areas of unchanging landcover class, the time series classification of Hermosilla et al. (2022) was used. Land cover permanence was calculated by summing the number of times each land cover class pixel was identified in the same pixel location. Reference rasters contain a numerical pixel value (i.e. 1 – open water; 2 – marsh; 3 – wet meadow; 4 – woody/shrub) that corresponds to each land cover in the input rasters. The 1984 land cover raster was chosen as the reference raster because this was the first year of the record, thereby providing a baseline or starting point from which to compare. The permanent land cover raster was then used within GEE to mask out permanent zones within the study floodplain that showed potential as training areas. Training pixels were then allocated within these training areas and used over the whole time-series. However, in the years with available higher resolution imagery (i.e., sporadically throughout the time series: Aerial photographs – 1984 to 1991, 2005, 2007, and 2009; Sentinel 2 – 2016 to 2022; Airborne LiDAR – 2018; UAV LiDAR and geotagged photos – 2022), which by expert interpretive identification of land cover class was possible to increase the number of training pixels in these years with more reference datasets. 

The model result is a single raster file including the four aforementioned land covers; also, the area (km2) of each land cover, overall accuracy, and Kappa coefficient of the classification will be displayed in the right bar of the GEE.

The historical land cover maps (Hermosilla et al., 2022)) used to create and identify the Land cover permanent zones are open access and are available at https://opendata.nfis.org/mapserver/nfis-change_eng.html
