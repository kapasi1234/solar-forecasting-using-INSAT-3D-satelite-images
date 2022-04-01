# solar-forecasting-using-INSAT-3D-satelite-images
Solar irradiance forecasting using INSAT-3D satellite images.
Algorithm is developed for solar iraddiance forecasting using INSAT-3D satellite images.
Images and data fron the INSAT-3D satellite which is a meteorological geostationary satelLite launched and monitored by the by the INDIAN SPACE RESEARCH ORGANIZATION(ISRO) is used in this project.
The satelitte data is open source and can be downloaded from https://www.mosdac.gov.in/open-data.
The satellite data can be downloaded in HDF as well as GEO-TIFF format. In this projet we have used the data in the hdf format sice it cointains the meta data as well as the channels which are specific for the project,however in some modeules geotiff format is also used and its uses will be extensivey discussed.
The entore algorithm is divided in 3 modules
The first is to download the required satelitte data from the ISRO website usig the sftp protocol, pythons library pysftp can be used to automaticaly downloaf thre data.
The second module involves calculatimg the satelite dynamic range,the values of the minimum and the maximum pixel value over the area of interest by processing the data for 3 months. These maximum piel value is calledthe cloudy pixel and the minimum pixel values is called the clear pixel or the syrface albedo.
The third module involves predicting the solar forecasting.
Two methods for calculatimg the forecast is used, one is block matching and the other one is DVL1 optical flow.
PVLIB is used to calculate the clear ky irradiance.
forecasted clear sky index is calculated from the forecasted cloud index.
This sky clearness index is then multiplied by the clear sky irradince to claculate the forcasted irradiance.
To calculate the forecast at a particular timestamp images from two prior timestampos are used.
Since satellite images ae used many geospatil libraries in python are used like rasterio, gdal,fiona,xarray.
OPENCV is used to perform the computer vision algorithmm to generate the cloud motion vectors that ultimately gnerated the cloud index for the forecasting.

