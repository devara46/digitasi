# Digitasi Peta 

## Georeference 

Python script for georeferencing scanned images, work on PNG and jpg.   

### Requirements 

- gdal 
- pandas 
- geopandas
- opencv-python
- openpyxl
- tqdm 

### Usage

To use, enter the following code in anaconda prompt

```
conda env create -f requirements.yml
```

activate the environment using

```
conda activate autogeo
```

and run the code on your favorite code compiler

If there are problem creating environment using requirements.yml, create the environment manually by using these codes

```
conda create -n autogeo

conda install -y pip

conda install -y gdal

pip install pandas geopandas opencv-python openpyxl tqdm

```

### Using Map Boundaries 

The code for georeferencing using the map boundaries was split into two parts. 

The first one was *get_expanded_bounds.ipynb*, which is used to get the reference coordinate for georeference. This script requires a single input file which is the SLS boundary file (could be in GPKG or Geo JSON) 

The Second one was *georeference_coord.ipynb*, which adds georeference to the scanned image using the original boundaries as reference. This script requires three-parameter to be provided: 

- SOURCE: which is the folder path of the image that will be georeferenced. 
- COORD: which is the result file from *get_expanded_bounds.ipynb*. 
- RESULT: which is the path to the folder where the georeferenced image will be stored.
- TEMP_FILE: folder path to save temporary file created during the process, will be deleted afterward.
- EPSG: coordinate reference system used.

### Using Printed Coordinates 

### Move files into their respective location

To automatically sort files, use *move_kode.ipynb* using the following parameter

- SOURCE: path for source folder.
- DEST: path for the result folder.
- KEYMAP: excel file containing the reference id for each location, for example see *Map Kode SLS ST2023.xlsx*.

### Limitation 
  
- The map has to be upright and the north of the map needs to face north.
- The algorithm to detect the map area from scanned images is still limited. 
- Doesn't work on zoomed-in map or inset. 
- The algorithm still has difficulties detecting the map if the border is covered (tainted or folded). 
- Only works on a single folder.

### Future plan 

- Add the capability to search entire directories 
- Add the capabilities to split the result based on the id 
