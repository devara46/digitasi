# Digitasi Peta 

## Georeference 

Python script for georeferencing scanned images, work on PNG and jpg.   

### Requirements 

- gdal 
- pandas 
- geopandas 
- opencv-python 

### Using Map Boundaries 

The code for georeferencing using the map boundaries was split into two parts. 
The first one was *get_expanded_bounds.ipynb*, which is used to get the reference coordinate for georeference. 
The Second one was *georeference_coord.ipynb*, which adds georeference to the scanned image using the original boundaries as reference. 

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
