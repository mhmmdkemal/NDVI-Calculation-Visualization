# NDVI Calculation Visualization
NDVI Calculation &amp; Visualization using Numpy, Rasterio, Folium &amp; Matplotlib

### Defining the Task

Image processing is a fundamental component of the project. The "images/" directory contains 43 GeoTIFFs (embedded in a TIFF file, it is a metadata standard that allows georeferencing information) from an area in Minnesota. Though optical imagery typically contains red, green, and blue bands (layers), these files contain only red and near-infrared (NIR) bands. These bands are critical for determining the health of vegetation, particularly with Normalized Difference Vegetation Index (NDVI).

The task is to load the imagery into a NumPy array and produce several outputs:
* A time series of the average NDVI over time. This is the average NDVI across each image.
* A mosaicked NumPy array with three bands. Mosaicking is a method of flattening information from many images into a single image. The values generated are:
  * Max, Mean, Median & Min NDVI

### Key concepts to know before starting 

##### What is a Normalized Difference Vegetation Index (NDVI)? 
* NDVI allows for the quantification of vegetation by measuring the difference between near-infrared(NIR), which vegetation strongly reflects & red light, which vegetation absorbs.  NDVI has a range between -1 to +1. The negative values often times are attributed to water while the closer to +1 the values are, it indicated the high possibility of being dense green leaves. On the other hand, if the NDVI is close to zero, this can be an indication of an urbanized area rather than water or dense green leaves. Refer to image below:

![picture alt](https://miro.medium.com/max/848/1*8Gof7Q8WZrwn4X4AozHn3Q.png "NDVI Calculation")

* For our analysis in this python script, we will be using SENTINEL-2 Imagery to calculate the NDVI. SENTINEL-2 has 13 spectral bands: four bands at 10 meters, six bands at 20 meters and three bands at 60 meters spatial resolution with an orbital swath width of 290 km. In order to calculate the NDVI using this type of imagery, we need Band 4 (red) and Band 8 (NIR) 

##### What are Spectral Bands? 
* Spectral bands are a limited range of values the satellite sensor is able to detect along a spectrum. Visible light is only a very small portion of all light waves as shown in the image below. 

![picture alt](http://www.justscience.in/wp-content/uploads/2017/05/electromagneticspectrum.jpg "Spectral Bands")

