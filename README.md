# Digitasi Peta 

## Georeference 

Python script for georeferencing scanned images, work on PNG and jpg.   

### Requirements 

- gdal 
- pandas 
- geopandas 
- opencv-python 

### Usage

To use, enter the following code in anaconda prompt

```
conda env create -f requirements.yml
```

and run the code on your favorite code compiler

### Using Map Boundaries 

The code for georeferencing using the map boundaries was split into two parts. 

The first one was *get_expanded_bounds.ipynb*, which is used to get the reference coordinate for georeference. This script requires a single input file which is the SLS boundary file (could be in GPKG or Geo JSON) 

The Second one was *georeference_coord.ipynb*, which adds georeference to the scanned image using the original boundaries as reference. This script requires three-parameter to be provided: 

- SOURCE: which is the folder path of the image that will be georeferenced. 
- COORD: which is the result file from *get_expanded_bounds.ipynb*. 
- RESULT: which is the path to the folder where the georeferenced image will be stored. 

### Using Printed Coordinates 

### Limitation 
  
- The map has to be upright and the north of the map needs to face north.
- The algorithm to detect the map area from scanned images is still limited. 
- Doesn't work on zoomed-in map or inset. 
- The algorithm still has difficulties detecting the map if the border is covered (tainted or folded). 
- Only works on a single folder 

### Future plan 

- Add the capability to search entire directories 
- Add the capabilities to split the result based on the id 
