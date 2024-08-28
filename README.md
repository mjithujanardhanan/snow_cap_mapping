# snow_cap_mapping
this project is aimed at developing a model which can map the snowcap from satellite images

# Introduction

The Indian Himalayas, characterized by their rugged terrain and extreme climatic
conditions, are home to vast expanses of snow-covered landscapes, playing
a critical role in regional hydrology, ecology, and livelihoods. Accurate
monitoring and mapping of snow cover in this region are essential for various
applications, including water resource management, climate change studies,
and hazard mitigation. Satellite remote sensing offers a powerful tool
for observing snow cover dynamics over large spatial extents; however, traditional
methods for snow cover mapping often encounter challenges in complex
mountainous terrains.
In recent years, the advent of machine learning (ML) techniques has provided
new avenues for improving the accuracy and efficiency of snow cover mapping
from satellite imagery. ML algorithms have demonstrated remarkable capabilities
in image classification tasks, leveraging complex patterns and spectral
information to accurately delineate snow-covered areas.
Here we are trying to use ML techniques to identify the pixels which contains
snow. We make use of landsat 8 data which is freely available on internet.

# What is done in this project

-> The primary data used in the project is landsat 8 satellite data. we download it from USGS earth explorer.

-> NDSI index: It is a spectral index commonly used in remote sensing to detect the presence
of snow in satellite imagery. NDSI is designed to highlight the contrast
between snow and other surfaces, such as vegetation or soil, based on their
reflectance properties in different spectral bands. Higher NDSI values typically
indicate a higher likelihood of snow cover, while lower values indicate less
snow cover or the presence of other surface types.

-> NDFSI ( Normalised Difference Forested Snow Index): It is a spectral index proposed in the paper "An effective fractional snow cover
Estimation method using deep feature snow Index" by Yuhan Wang, Lingjia
Gu[1]. This index is a derivative of NDSI index but instead of using visible
bands this index makes use of Near infrared band and SWIR band of landsat
8 data to predict the snow pixels.

-> QGIS: We use raster calculator function from QGIS to generate NDFSI mask for each for the downloaded data. 

-> Thresholding: We threshold the mask at a value of 0.4 to create a binary image.( >0.4 means snow, this value is commonly used one). hence our dataset is created.

-> Training: We use a unet architecture to train our model. With Green, NIR, SWIR bands as input and binary mask as output.

note:: The dataset used:: https://www.kaggle.com/datasets/jithuj/snowcap-northsikkim
