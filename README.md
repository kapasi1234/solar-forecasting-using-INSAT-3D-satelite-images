# solar-forecasting-using-INSAT-3D-satellite-images
Solar irradiance forecasting using INSAT-3D satellite images.
The algorithm is developed for solar irradiance forecasting using INSAT-3D satellite images.
Images and data from the INSAT-3D satellite, a meteorological geostationary satellite launched and monitored by the INDIAN SPACE RESEARCH ORGANIZATION(ISRO) are used in this project.
The satellite data is open source and can be downloaded from https://www.mosdac.gov.in/open-data.
The satellite data can be downloaded in HDF as well as GEO-TIFF format. In this project we have used the data in the HDF format since it contains the metadata as well as the channels which are specific to the project, however, in some modules, GeoTIFF format is also used and its uses will be extensively discussed.
The entire algorithm is divided into 3 modules
The first is to download the required satellite data from the ISRO website using the sftp protocol, pythons library pysftp can be used to automatically download the data.
The second module involves calculating the satellite dynamic range, and the values of the minimum and the maximum pixel value over the area of interest by processing the data for 3 months. This maximum pixel value is called the cloudy pixel and the minimum pixel value is called the clear pixel or the surface albedo.
The third module involves predicting solar forecasting.
Two methods for calculating the forecast are used, one is block matching and the other one is DVL1 optical flow.
PVLIB is used to calculate the clear sky irradiance.
The forecasted sky index is calculated from the predicted cloud index.
This sky clearness index is then multiplied by the clear sky irradiance to calculate the forecasted irradiance.
To calculate the forecast at a particular timestamp images from two prior timestamps are used.
Since satellite images are used many geospatial libraries in python are used like rasterio, gdal, Fiona, and array.
OpenCV is used to perform the computer vision algorithms to generate the cloud motion vectors that ultimately generate the cloud index for forecasting.
