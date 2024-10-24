# Medial-Axis-Centerline-Width
It will include Google Earth Engine Script, Apps, and dataset to find river width and centerline.

## Installation of required packages
For jupyter and ArcGIS Pro notebook use this command: install required libraries if not installed by uncommenting it:

#!pip install geopandas

#!pip install numpy

#!pip install pandas

#!pip install rasterio

#!pip install matplotlib

Other options, installing it by using the package manager in ArcGIS Pro, to add necessary packages to operate this program such as rasterio, geopandas, numpy, pandas, and matplotlib.

## Usage Guide
The easiest and quickest way to use the cross-section extraction visualization tool is to run it from ArcPro Toolboxes, where the functions can be directly loaded without setup. The tutorial for using the tool is shared on my YouTube channel (learnsomethingtoday): [https://youtu.be/J0KKxBf-vLI](https://youtu.be/POs02W3LgS8)

### Example usage
extract_and_visualize_cross_sections('Data\Shapefiles\Cross sections.shp', 'Data\DEM.tif', n_points=3, csv_output_dir='Samples', png_output_dir='Samples')

### Explanation
Here's an explanation of the provided code for extracting river width and centerline from the JRC Global Surface Water dataset using the Zhang-Suen thinning algorithm:

1. **Loading the Dataset**:
   - The code loads the JRC Global Surface Water dataset and selects the 'occurrence' band, which indicates the frequency of water presence.

2. **Creating a Water Mask**:
   - A binary water mask is created where water occurrence is greater than 50%. This mask highlights areas that are predominantly water.

3. **Zhang-Suen Thinning Algorithm**:
   - The `Zhang_Suen` function applies the Zhang-Suen thinning algorithm to extract the centerline of the water bodies. This algorithm iteratively removes pixels from the edges of the water regions while preserving the connectivity and topology of the centerline.

4. **Iterations**:
   - The algorithm runs for a specified number of iterations. In each iteration, it performs two main steps:
     - **First Iteration**: Checks conditions on the neighborhood of each pixel to determine if it should be removed.
     - **Second Iteration**: Similar checks are performed with slightly different conditions to further refine the centerline.

This process results in a thinned representation of the water bodies, effectively extracting their centerlines and width.

## Acknowledgement
I acknowledge the 
YouTube video made by the GeoDev Tools channel for the video of the crosssection extractor and the valuable feedback 



## Contact
Open for collaboration and welcome any valuable feedback or suggestions for improvement. If you have any queries about the algorithm, open for discussion and contact:
pthapa2@crimson.ua.edu.

## Future work
Currently, it provides CSVs and raster (.tif) files and saves it in the ArcGIS Pro content.
