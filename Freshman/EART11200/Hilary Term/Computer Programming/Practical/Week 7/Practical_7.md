---
title: "Practical_7"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Practical/Week 7/Practical_7.ipynb"
type: notebook
---

# Practical 7: Pandas data discovery - Raster vs. Vector Data

<div class="alert alert-block alert-success">
<b>Objectives:</b> In this practical we will use the GeoPandas package to load data from files and visualise our results on a map. We will introduce the concepts of both raster and vector data, and how these underline the approach of <b>Geographic Information Systems, or GIS</b>. To do this we will open and manipulate datafiles that contains information on bedrock, quarries and flooding risk across the UK. We will do this through the following activities:

 - 1) [Introduction: Raster vs. Vector Data in Environmental Science](#Part1)
      * [Exercise 1: Create a map showing locations with only limestone bedrock](#Exercise1)
 - 2) [Adding vector point data and combining GeoPandas dataframes](#Part2)
      * [Exercise 2: Plot the distribution of bedrock under collieries across the UK](#Exercise4)
      * [Exercise 3: Create a map of colliery location and underlying bedrock in Greater Manchester](#Exercise5)
      * [Exercise 4: Plot the location of flood risk zones across Greater Manchester](#Exercise5)
 - 3) [Calculating distances between points and polygons](#Part3)
      * [Exercise 5: Create a map of flooding and substation risk for the Stockport District](#Exercise6)

As with our other notebooks, we will provide you with a template for plotting the results. Also please note that you should not feel pressured to complete every exercise in class. These practicals are designed for you to take outside of class and continue working on them. Proposed solutions to all exercises can be found in the 'Solutions' folder.

Please do not worry about trying to remember all of the syntax in the code we provide. As noted in the lectures, this course is aimed at building experience in using Python and many of its features. Even seasoned professionals have to look up solutions from old files or online!
</div>

<div class="alert alert-block alert-danger">
<b> Using Google Colabs </b> Please note that the first code block ensures that we can access our files IF we are running this example on Google Colab. Please run this code block and, if you are not on Google Colab, you will recieve a message that confirms this.
</div>

```python
if 'google.colab' in str(get_ipython()):
    !pip install contextily
else:
     print('Not running on CoLab')

if 'google.colab' in str(get_ipython()):
    from google.colab import drive
    mount='/content/gdrive'
    print("Colab: mounting Google drive on ", mount)
    drive.mount(mount)
    drive_root = mount + "/My Drive/Colab Notebooks/DEES_first_year/DEES_programming_course"
    # Change to the directories to get data files
    print("\nColab: Changing directory to ", drive_root)
    %cd $drive_root
else:
    print('Not running on CoLab')

# The following is a new addition for 2025 where the UoM uses a Jupyterhub instance which is fixed to Python3.12.
# If the notebook is running on this particular JupyterHub, we set PROJ paths explicitly to avoid CRS lookup issues.

import os

IN_JUPYTERHUB = any(k.startswith("JUPYTERHUB_") for k in os.environ)

if IN_JUPYTERHUB:
    print("Running on JupyterHub — PROJ paths set")
    os.environ["PROJ_DATA"] = "/opt/conda/envs/gis-practical/share/proj"
    os.environ["PROJ_LIB"]  = "/opt/conda/envs/gis-practical/share/proj"
```

    Not running on CoLab

# 1) Introduction: Raster vs. Vector Data in Environmental Science  <a name="Part1">

In the previous notebook we worked with geospatial data in the form of coordinates of volcanic eruptions. This gave us an opportunity to introduce the Pandas dataframe functionality within Python. We also used the module `Cartopy` for plotting said data on a map, thus creating a useful visualisation of data that could be used to build expert analysis, or learning, around. In most areas of environmental science spatial data is pivotal for analysis and visualization; So much so that it is useful we briefly extend our geospatial learning to include more *formal* definitions of processes and data types.

If you start to work more frequently with geospatial data, you will inevitably come across **Geographic Information Systems**, or more commonly referred to as **GIS**. GIS is a system used for capturing, storing, checking, and displaying data related to positions on Earth's surface. It helps analysts understand patterns, relationships, and geographic context. In our course so far we have structured our learning around types of data storage and ways to create and access data. When we refer to GIS we might consider this a seperate field by itself. Indeed, there are multiple components of GIS:

- **Data**: The core of GIS, encompassing geographical (spatial) data and attribute (descriptive) data.
- **Tools for Analysis**: GIS provides tools to analyze and interpret data, revealing patterns and relationships.
- **Visualization**: Beyond maps, GIS allows for sophisticated visual representations like 3D models and thematic maps.

How is this different from what we have looked at so far? GIS essentially is a system for:

- **Layering Information**: GIS layers different types of data (like roads, rivers, population) to show relationships and patterns.
- **Spatial Analysis**: It can perform complex spatial analyses, answering questions like "What is the shortest route?" or "What areas are at high risk for flooding?"

GIS is often, and incorrectly, thought to remain a tool solely within the field of Geography. GIS is not just for geographers; it's used in history, archaeology, environmental science, engineering, and more. Many use dedicated GIS software products to perform the above. The most common include:

- **ArcGIS**: Developed by Esri, ArcGIS is one of the most widely used GIS software tools globally. It offers a suite of professional GIS applications, including ArcMap, ArcGIS Pro, and various online tools. It's known for its extensive capabilities in data visualization, analysis, and management.
- **QGIS (Quantum GIS)**: An open-source alternative to ArcGIS, QGIS is highly popular among users who prefer open-source. It offers a  set of features for mapping and spatial analysis. Its compatibility with various file formats and extensible nature through plugins makes it a versatile choice.
- **Google Earth Engine**: An advanced cloud-based tool for planetary-scale environmental data analysis. It's known for its massive archive of satellite imagery and geospatial datasets, which are useful for large-scale environmental monitoring and analysis.
- **....**

Tools vary widely in functionality, complexity, and cost, catering to different needs and skill levels. In this notebook we will find that there are modules, thus tools, in Python that can perform the aforementioned GIS functionality of layering through to spatial analysis. However we need to add new formal defintions to the core of GIS, the underlying data, before we begin.

## Raster and Vector Data

Geospatial data primarily comes in two forms: **raster** and **vector** data. Understanding their differences, applications, and formats is important in the field.

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/featured3.png?raw=true)

https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical_5_figure1.png?raw=true

### Raster Data

Raster data represents the Earth's surface as a matrix of cells, with each cell holding a value to represent a certain attribute like temperature or elevation. You can think of this as a checkerboard placed over the ground, where there is a value in each cell of the board. This may represent any variable of interest such as temperature, soil moisture, height and so on. The left hand side of figure 1 illustrates this concept. We can imagine opening a raster dataset in a wide range of software products, including Excel if we really wanted to.

### Vector Data

Vector data uses geometric shapes (points, lines, polygons) to represent spatial features like locations (wells, weather stations), paths (rivers, roads), and areas (lakes, political boundaries). We have already encoutered points in the previous notebook. Coordinates of single locations as a function of time resemble a raster dataset.

Key characteristics and examples of both **raster** and **vector** data are given in the table below. You can also find common formats used for storing the data. That isnt to say we will stop using CSV files. However, we quickly find that CSV files are rather limited when we start to work with data that is more complex than tabular structures. CSV files are also relatively inefficient so larger quantities of data require bespoke formats. We have already noted that Pandas can work with a wide range of data formats. For example, JSON stands for JavaScript Object Notation. It is a lightweight data-interchange format that is easy for humans to read and write, and easy for machines to parse and generate.

If you were to open a GEOJSON file in a text editor you might find something similar to the following example containing a single point feature:

```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [-73.9617, 40.6629]
      },
      "properties": {
        "name": "Brooklyn",
        "borough": "Kings",
        "state": "NY"
      }
    }
  ]
}
```

In this example, the GeoJSON object is a FeatureCollection. It contains an array of Feature objects. Each Feature has a geometry (in this case, a Point with coordinates) and properties (additional data about the feature). GeoJSON introduces specific types such as Point, LineString, Polygon, MultiPoint, MultiLineString, MultiPolygon, and GeometryCollection. Each of these types is used to represent different types of geographical features. We will be working with SHP files [see table below - Shapefiles] in this notebook. I cant actually provide you with an example of a SHP file per the GeoJOSN file. Shapefiles consist of several files that work together, and they contain binary data which is not human-readable in the same way.  They are however much more efficient in terms of storage requirements. The Shapefile format, commonly known as .shp, was created by Esri (Environmental Systems Research Institute), a leading company in the field of geographic information systems (GIS). Esri developed the Shapefile format in the early 1990s for their GIS software, and it quickly became a popular format for storing geographical data due to its simplicity and ease of use.

| Data Type | Key Characteristics                                                                 | Common Formats                                  | Examples                                             |
|-----------|-------------------------------------------------------------------------------------|-------------------------------------------------|-----------------------------------------------------|
| Raster    | - Grid format (rows and columns) <br> - Cell values for attributes <br> - Resolution dependent | - GeoTIFF (.tif) <br> - ERDAS IMAGINE (.img) <br> - Digital Elevation Models (DEM) | - Satellite imagery <br> - Elevation data (DEMs) <br> - Land cover maps |
| Vector    | - Shape-based (points, lines, polygons) <br> - Precise location <br> - Attribute richness | - Shapefile (.shp) <br> - GeoJSON (.geojson) / TopoJSON (.topojson) <br> - KML/KMZ (.kml/.kmz) | - Map of geological sample locations <br> - River network diagrams <br> - Boundary maps for geological formations |

You may well ask what category our coordinate data from the previous notebook would fall within. That would be classed as *point vector* data since it was not provided under a fixed grid, but rather a set of latitude and longitude values for each eruption. In this notebook we will also work with polygon and line vector data. Choosing between raster and vector data depends on the data's nature and the analysis requirements.

- **Analysis type**: Some analyses favor the continuous nature of raster data; others need the precision of vector data.
- **Data integration**: Often, integrating both raster and vector data is necessary.
- **Visualization**: Raster and vector formats differ significantly in mapping and visualization.

Understanding raster and vector data's differences, along with their specific formats, is essential for geoscientists to effectively analyze, integrate, and visualize spatial information.

One more point of discussion before we begin..

A slight *tweak* to Pandas is required to deal with line and polygon vector data. The good news is that someone has already done this for us. A module called GeoPandas is built exactly to deal with line and polygon data.

## What is GeoPandas?

GeoPandas is an open-source project that makes working with geospatial data in Python easier. It extends the datatypes used by pandas to allow spatial operations on geometric types. Geometric operations are performed by `shapely`. GeoPandas further depends on `fiona` for file access and `matplotlib` for plotting. These are all modules that are installed when we install GeoPandas using the `conda` package manager. Figure xx below provides a simple illustration of GeoPandas. Features of GeoPandas include:

- **Geospatial Data Handling**: Simplifies handling of geospatial data (like shapefiles, GeoJSON) in Python.
- **Integration with pandas**: Builds upon and extends pandas, making it easy to work with geospatial data using familiar pandas functionalities.
- **Geometry Operations**: Enables geometry operations (like calculating area, distance, buffering) directly on GeoDataFrame.
- **Plotting and Visualization**: Offers straightforward plotting of geospatial data, which integrates well with `matplotlib`.

The GeoDataFrame is the core data structure in GeoPandas, which can store geometry columns and perform spatial operations.

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/geopandas.png?raw=true)

notice how we still retain the concept of an index, but have a seperate column that can store shapes. We will load a `.shp` file that contains information on bedrock geology across the UK. First we will import relevant modules that we will use across this notebook. These are:

 - GeoPandas
 - Contextily [a small Python 3 (3.7 and above) package to retrieve tile maps from the internet](https://contextily.readthedocs.io/en/latest/). It can add those tiles as a basemap to matplotlib figures, which gives us the underlying map.
 - Matplotlib. As usual...this deals with all of our plotting requirements.

```python
# import the modules, using standard naming convention.
import geopandas as gpd
import contextily as cx
import matplotlib.pyplot as plt
%matplotlib inline
import os
from os import path

path=os.getcwd()
# Our file has the following path and name - notice the extension .shp
file = path+"/data/digmap625_bedrock_arc/625k_V5_BEDROCK_Geology_Polygons.shp"
# Like Pandas, GeoPandas has a read_file function. Im creating a GeoDataframe called 'gdf'
gdf = gpd.read_file(file)

# Preview the GeoDataframe to the screen
gdf
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>LEX</th>
      <th>LEX_D</th>
      <th>LEX_RCS</th>
      <th>RCS</th>
      <th>RCS_X</th>
      <th>RCS_D</th>
      <th>RANK</th>
      <th>BED_EQ</th>
      <th>BED_EQ_D</th>
      <th>MB_EQ</th>
      <th>...</th>
      <th>BGSREF_GP</th>
      <th>BGSREF_RK</th>
      <th>SHEET</th>
      <th>VERSION</th>
      <th>RELEASED</th>
      <th>NOM_SCALE</th>
      <th>NOM_OS_YR</th>
      <th>NOM_BGS_YR</th>
      <th>MSLINK</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>UISD-MFIR</td>
      <td>MFIR</td>
      <td>MFIR</td>
      <td>MAFIC IGNEOUS-ROCK</td>
      <td>INTRUSION</td>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>NoPar</td>
      <td>...</td>
      <td>773</td>
      <td>773</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>18166</td>
      <td>POLYGON ((274375.248 555042.401, 274315.421 55...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>UISD-MFIR</td>
      <td>MFIR</td>
      <td>MFIR</td>
      <td>MAFIC IGNEOUS-ROCK</td>
      <td>INTRUSION</td>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>NoPar</td>
      <td>...</td>
      <td>773</td>
      <td>773</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>18166</td>
      <td>POLYGON ((273618.809 553462.498, 273661.625 55...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>UISD-MFIR</td>
      <td>MFIR</td>
      <td>MFIR</td>
      <td>MAFIC IGNEOUS-ROCK</td>
      <td>INTRUSION</td>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>NoPar</td>
      <td>...</td>
      <td>773</td>
      <td>773</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>18166</td>
      <td>POLYGON ((270985.247 554515.841, 270985.247 55...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>UISD-MFIR</td>
      <td>MFIR</td>
      <td>MFIR</td>
      <td>MAFIC IGNEOUS-ROCK</td>
      <td>INTRUSION</td>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>NoPar</td>
      <td>...</td>
      <td>773</td>
      <td>773</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>18166</td>
      <td>POLYGON ((273409.542 555538.671, 273361.680 55...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>UISD-MFIR</td>
      <td>MFIR</td>
      <td>MFIR</td>
      <td>MAFIC IGNEOUS-ROCK</td>
      <td>INTRUSION</td>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>NoPar</td>
      <td>...</td>
      <td>773</td>
      <td>773</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>18166</td>
      <td>POLYGON ((271835.801 556443.700, 271770.116 55...</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>11239</th>
      <td>WHCK</td>
      <td>WHITE CHALK SUBGROUP</td>
      <td>WHCK-CHLK</td>
      <td>CHLK</td>
      <td>CHLK</td>
      <td>CHALK</td>
      <td>SUBGROUP</td>
      <td>NotAp</td>
      <td>Not Applicable</td>
      <td>NotAp</td>
      <td>...</td>
      <td>420</td>
      <td>430</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>17472</td>
      <td>POLYGON ((633760.875 140660.672, 633059.688 13...</td>
    </tr>
    <tr>
      <th>11240</th>
      <td>WHCK</td>
      <td>WHITE CHALK SUBGROUP</td>
      <td>WHCK-CHLK</td>
      <td>CHLK</td>
      <td>CHLK</td>
      <td>CHALK</td>
      <td>SUBGROUP</td>
      <td>NotAp</td>
      <td>Not Applicable</td>
      <td>NotAp</td>
      <td>...</td>
      <td>420</td>
      <td>430</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>17472</td>
      <td>POLYGON ((577986.813 169677.828, 577981.250 16...</td>
    </tr>
    <tr>
      <th>11241</th>
      <td>WHCK</td>
      <td>WHITE CHALK SUBGROUP</td>
      <td>WHCK-CHLK</td>
      <td>CHLK</td>
      <td>CHLK</td>
      <td>CHALK</td>
      <td>SUBGROUP</td>
      <td>NotAp</td>
      <td>Not Applicable</td>
      <td>NotAp</td>
      <td>...</td>
      <td>420</td>
      <td>430</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>17472</td>
      <td>POLYGON ((561716.396 179667.794, 561910.362 17...</td>
    </tr>
    <tr>
      <th>11242</th>
      <td>WHCK</td>
      <td>WHITE CHALK SUBGROUP</td>
      <td>WHCK-CHLK</td>
      <td>CHLK</td>
      <td>CHLK</td>
      <td>CHALK</td>
      <td>SUBGROUP</td>
      <td>NotAp</td>
      <td>Not Applicable</td>
      <td>NotAp</td>
      <td>...</td>
      <td>420</td>
      <td>430</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>17472</td>
      <td>POLYGON ((585387.000 346343.938, 585321.000 34...</td>
    </tr>
    <tr>
      <th>11243</th>
      <td>WHCK</td>
      <td>WHITE CHALK SUBGROUP</td>
      <td>WHCK-CHLK</td>
      <td>CHLK</td>
      <td>CHLK</td>
      <td>CHALK</td>
      <td>SUBGROUP</td>
      <td>NotAp</td>
      <td>Not Applicable</td>
      <td>NotAp</td>
      <td>...</td>
      <td>420</td>
      <td>430</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>17472</td>
      <td>POLYGON ((600000.000 347101.531, 601624.750 34...</td>
    </tr>
  </tbody>
</table>
<p>11244 rows × 56 columns</p>
</div>

Notice how GeoPandas, like Pandas, has created its own indexing system of assigning a number to each row. There are also mulitple columns. Unfortunately you will often find it is difficult to obtain 'meta data' associated with records. Meta-data provides us with important information, such as when data was collected and so on. In this instance, I want to create a map using the column **RCS_D** which describes the dominant type of rock. To place this on a map, I need coordinates.  If you scroll to the right hand edge if the dataframe you will find a column called `geometry`. This contains `POLYGON` with what appear to be a series of floating point numbers. This brings us on to an important check-point; Coordinate Reference Systems.

## Coordinate Reference System (CRS)

Before we create our map using the information provided in this file, we need to check what system is being used to represent the coordinates. If you take a look at the column `geometry` we can clearly see these do not represent latitude and longitude numbers. But why? A Coordinate Reference System (CRS) defines how the two-dimensional, projected map in your GeoDataFrame relates to real places on the earth. CRS can be represented in various formats, such as EPSG codes. EPSG codes are short identifiers assigned to coordinate reference system (CRS) definitions. These codes are standardized and maintained by the EPSG (European Petroleum Survey Group) Geodetic Parameter Dataset. EPSG codes cover both geographic coordinate systems (GCS) and projected coordinate systems (PCS). A GCS uses latitude and longitude to define locations on the earth's surface, while a PCS provides a flat, two-dimensional representation of the earth.

The following table lists some of the most frequently used EPSG codes in GIS, along with their descriptions:

| EPSG Code | CRS Name                   | Description                                                                                   |
|-----------|----------------------------|-----------------------------------------------------------------------------------------------|
| EPSG:4326 | WGS 84                     | Standard for global geographic coordinate system, used in GPS and for global datasets.        |
| EPSG:3857 | WGS 84 / Pseudo-Mercator   | Also known as Web Mercator. Common for web mapping services like Google Maps and OpenStreetMap. |

**Key Points**:
- **EPSG:4326** is widely used for datasets that span the entire globe. It represents coordinates in latitude and longitude.
- **EPSG:3857** is used for displaying maps on web applications, offering a compromise between a spherical and flat representation of the earth.
- ...
- **Using EPSG codes ensures that spatial data from different sources can be combined and analyzed accurately. Correct CRS selection (via EPSG codes) is crucial for accurate distance and area measurements, especially over large geographic extents. This is crucial when combining data from different sources to ensure they align correctly.**

So we need to check what Coordinate Reference System (CRS) our bedrock datafile is in. To do this, we can use the ```python .crs ``` property of our GeoDataframe as per the code box below.

```python
gdf.crs
```

    <Projected CRS: PROJCS["OSGB36 / British National Grid",GEOGCS["OS ...>
    Name: OSGB36 / British National Grid
    Axis Info [cartesian]:
    - [east]: Easting (metre)
    - [north]: Northing (metre)
    Area of Use:
    - undefined
    Coordinate Operation:
    - name: unnamed
    - method: Transverse Mercator
    Datum: Ordnance Survey of Great Britain 1936
    - Ellipsoid: Airy 1830
    - Prime Meridian: Greenwich

We are told this data is stored using a projected coordinate system. More specifically, OSGB36. OSGB36 was historically developed to provide a consistent and accurate mapping framework for the UK.  For applications that require global positioning, such as GPS, data from OSGB36 often needs to be transformed to a more universally recognized datum like EPSG:4326. We are going to convert all of our loaded vector and raster files into EPSG:3857. As we combine data from different sources, we need to ensure they are based on the same CRS. Fortunately, GeoPandas allows us to move between different systems. In the code snippet below, we create reference to a new GeoDataframe using the `.to_crs` function. We also preview it and notice that data in the geometry column has indeed changed.

```python
gdf_wm = gdf.to_crs(epsg=3857)
gdf_wm
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>LEX</th>
      <th>LEX_D</th>
      <th>LEX_RCS</th>
      <th>RCS</th>
      <th>RCS_X</th>
      <th>RCS_D</th>
      <th>RANK</th>
      <th>BED_EQ</th>
      <th>BED_EQ_D</th>
      <th>MB_EQ</th>
      <th>...</th>
      <th>BGSREF_GP</th>
      <th>BGSREF_RK</th>
      <th>SHEET</th>
      <th>VERSION</th>
      <th>RELEASED</th>
      <th>NOM_SCALE</th>
      <th>NOM_OS_YR</th>
      <th>NOM_BGS_YR</th>
      <th>MSLINK</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>UISD-MFIR</td>
      <td>MFIR</td>
      <td>MFIR</td>
      <td>MAFIC IGNEOUS-ROCK</td>
      <td>INTRUSION</td>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>NoPar</td>
      <td>...</td>
      <td>773</td>
      <td>773</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>18166</td>
      <td>POLYGON ((-440750.842 7337513.465, -440854.565...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>UISD-MFIR</td>
      <td>MFIR</td>
      <td>MFIR</td>
      <td>MAFIC IGNEOUS-ROCK</td>
      <td>INTRUSION</td>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>NoPar</td>
      <td>...</td>
      <td>773</td>
      <td>773</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>18166</td>
      <td>POLYGON ((-441985.281 7334731.896, -441909.793...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>UISD-MFIR</td>
      <td>MFIR</td>
      <td>MFIR</td>
      <td>MAFIC IGNEOUS-ROCK</td>
      <td>INTRUSION</td>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>NoPar</td>
      <td>...</td>
      <td>773</td>
      <td>773</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>18166</td>
      <td>POLYGON ((-446601.788 7336431.621, -446599.179...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>UISD-MFIR</td>
      <td>MFIR</td>
      <td>MFIR</td>
      <td>MAFIC IGNEOUS-ROCK</td>
      <td>INTRUSION</td>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>NoPar</td>
      <td>...</td>
      <td>773</td>
      <td>773</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>18166</td>
      <td>POLYGON ((-442449.345 7338328.683, -442532.332...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>UISD-MFIR</td>
      <td>MFIR</td>
      <td>MFIR</td>
      <td>MAFIC IGNEOUS-ROCK</td>
      <td>INTRUSION</td>
      <td>UISD</td>
      <td>UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...</td>
      <td>NoPar</td>
      <td>...</td>
      <td>773</td>
      <td>773</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>18166</td>
      <td>POLYGON ((-445222.788 7339823.915, -445336.698...</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>11239</th>
      <td>WHCK</td>
      <td>WHITE CHALK SUBGROUP</td>
      <td>WHCK-CHLK</td>
      <td>CHLK</td>
      <td>CHLK</td>
      <td>CHALK</td>
      <td>SUBGROUP</td>
      <td>NotAp</td>
      <td>Not Applicable</td>
      <td>NotAp</td>
      <td>...</td>
      <td>420</td>
      <td>430</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>17472</td>
      <td>POLYGON ((149030.968 6642109.528, 147869.541 6...</td>
    </tr>
    <tr>
      <th>11240</th>
      <td>WHCK</td>
      <td>WHITE CHALK SUBGROUP</td>
      <td>WHCK-CHLK</td>
      <td>CHLK</td>
      <td>CHLK</td>
      <td>CHALK</td>
      <td>SUBGROUP</td>
      <td>NotAp</td>
      <td>Not Applicable</td>
      <td>NotAp</td>
      <td>...</td>
      <td>420</td>
      <td>430</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>17472</td>
      <td>POLYGON ((62031.488 6692037.027, 62020.676 669...</td>
    </tr>
    <tr>
      <th>11241</th>
      <td>WHCK</td>
      <td>WHITE CHALK SUBGROUP</td>
      <td>WHCK-CHLK</td>
      <td>CHLK</td>
      <td>CHLK</td>
      <td>CHALK</td>
      <td>SUBGROUP</td>
      <td>NotAp</td>
      <td>Not Applicable</td>
      <td>NotAp</td>
      <td>...</td>
      <td>420</td>
      <td>430</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>17472</td>
      <td>POLYGON ((36526.794 6708936.970, 36820.807 670...</td>
    </tr>
    <tr>
      <th>11242</th>
      <td>WHCK</td>
      <td>WHITE CHALK SUBGROUP</td>
      <td>WHCK-CHLK</td>
      <td>CHLK</td>
      <td>CHLK</td>
      <td>CHALK</td>
      <td>SUBGROUP</td>
      <td>NotAp</td>
      <td>Not Applicable</td>
      <td>NotAp</td>
      <td>...</td>
      <td>420</td>
      <td>430</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>17472</td>
      <td>POLYGON ((84610.507 6979741.094, 84499.792 697...</td>
    </tr>
    <tr>
      <th>11243</th>
      <td>WHCK</td>
      <td>WHITE CHALK SUBGROUP</td>
      <td>WHCK-CHLK</td>
      <td>CHLK</td>
      <td>CHLK</td>
      <td>CHALK</td>
      <td>SUBGROUP</td>
      <td>NotAp</td>
      <td>Not Applicable</td>
      <td>NotAp</td>
      <td>...</td>
      <td>420</td>
      <td>430</td>
      <td>625k_V5_Bedrock</td>
      <td>5.17</td>
      <td>11- 2-2008</td>
      <td>625000</td>
      <td>2005 HC</td>
      <td>2007</td>
      <td>17472</td>
      <td>POLYGON ((108859.856 6980028.266, 111510.001 6...</td>
    </tr>
  </tbody>
</table>
<p>11244 rows × 56 columns</p>
</div>

Now we are close to producing our first map. GeoDataframes have a `.plot` function, like Pandas dataframes. By default they will plot the information stored within the geometry column. In the following short code snippet there are multiple operations and options provided. Lets break them down a little to try and understand a little more.

<div class="alert alert-block alert-info">

 - Create reference to a new axis, 'ax1', which is created when calling the `.plot` function. A number of plot options and arguments are provided. This include:
 > alpha - a level of transpareny for the bedrock layers. I would like to see some of the underlying map
 > column - specify the column by which I want to classify the different polygons, thus label.
 > edgecolor - colour to seperate the polygons
 > cmap - the colour scheme to use for the different categories. There are many in Matplotlib: [https://matplotlib.org/stable/users/explain/colors/colormaps.html]
 > legend - do I want a legend? Yes.
 > legend_kwds - these are specific keywords that define the style and placing of the legend, which you do not need to remember!

 - Use contextily to add a basemap to the above axis. Contextily works by providing different styles of tiles to our figures. The default is to use OpenStreetMap, which looks like Google Maps. When we call the function `.add_basemap` we have to tell Contextily which axis to use, and the CRS system to map on to. It does all ofthe alignment for us! Note this is a web service so if not connected to the internet this may not work.

</div>

```python
# Create an axis [ax1] that has the information held within the gdf_wm dataframe. Provide styling and colouring option
ax1 = gdf_wm.plot(figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k", cmap="gist_ncar",legend=True, legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5),"fontsize":7})
# Use the Contextily module to add a basemap underneath axes (ax1), which will look like OpenStreetMap. We make sure Contextily uses the same 'CRS' system by supplying this as an argument
cx.add_basemap(ax1, crs='EPSG:3857')
plt.show()
```

![png](output_11_0.png)

## Selecting a subset of data.

In our previous notebook we were able to select a subset of a dataframe. For example, we only wanted to plot data from eruptions that occured in 2019. To do this we created a reduced dataframe created by the following code:

```python
data[data['Start Year'] == 2019]
```

I dont have any specific numeric criteria in this example. Rather, I want to select a subset according to the enries in the column **RCS_D**. The `.str.contains()` function in Pandas (and by extension, GeoPandas, since GeoPandas is an extension of Pandas) is used to check if each string in a Series or Index contains a specified pattern or substring. It's commonly used for filtering data based on string patterns. In our case, this means I can select a subset of our dataframe that has certain keywords. In the example below, I recreate the above map but only for entries that contain 'SANDSTONE' in the column **RCS_D**. Note that I first create a new GeoDataframe called `gdf_wm_new` based on this criteria.

```python
gdf_wm_new = gdf_wm[gdf_wm["RCS_D"].str.contains('SANDSTONE')]
ax2 = gdf_wm_new.plot(figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k", cmap="gist_ncar",legend=True, legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5),"fontsize":7})
cx.add_basemap(ax2, crs='EPSG:3857')
plt.show()
```

![png](output_13_0.png)

<div class="alert alert-block alert-success">
<b> Exercise 1: Create a map showing locations with only limestone bedrock. <a name="Exercise1"></a>  </b> Repeat the above code demonstration but selecting only locations with limestone deposits. I have chosen the name of a new dataframe for you.
</div>

```python
# -------'INSERT CODE HERE'-------
gdf_wm_ex1 = gdf_wm[gdf_wm["RCS_D"].str.contains('LIMESTONE')]
ax3 = gdf_wm_ex1.plot(figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k", cmap="gist_ncar",legend=True, legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5),"fontsize":7})
cx.add_basemap(ax3, crs='EPSG:3857')
plt.show()
# --------------------------------
```

![png](output_15_0.png)

# 2) Adding vector point data and combining GeoPandas dataframes   <a name="Part2">

## Adding vector point data

We now want to add a new layer to our map. GIS systems are built to add layers. To demonstrate this I obtained a Shapefile containing information on the location of Collieries across the UK, from the [National Library of Scotland](https://data.nls.uk/projects/mapping-quarries-and-collieries/) as poart of their [GB1900 gazetteer project](https://data.nls.uk/data/map-spatial-data/gb1900/). A colliery refers to a coal mine and its associated buildings, where coal is extracted from underground. In the context of a colliery, the term encompasses not only the physical mine shafts but also the infrastructure and facilities used for the extraction and processing of coal. The type of bedrock underlying a colliery can vary significantly depending on the geological characteristics of the region where the coal mine is located. Coal is formed from the remains of ancient plants and animals that accumulated in swampy environments millions of years ago, eventually becoming buried under layers of sediment. Over time, these organic deposits were subjected to high pressure and heat, transforming into coal.
Our task is to use GeoPandas to plot these locations over our existing bedrock map. First we need to load this new Shapefile.

```python
# make referene to the location of the .shp file and then use GeoPandas to load in and then preview.
file_colliery = path+"/data/collieries/collieries.shp"
cdf = gpd.read_file(file_colliery)
cdf
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>pin_id</th>
      <th>final_text</th>
      <th>nation</th>
      <th>local_auth</th>
      <th>parish</th>
      <th>osgb_east</th>
      <th>osgb_north</th>
      <th>latitude</th>
      <th>longitude</th>
      <th>notes</th>
      <th>field_11</th>
      <th>field_12</th>
      <th>field_13</th>
      <th>field_14</th>
      <th>field_15</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>582454ab2c66dc2d42047bf8</td>
      <td>Witley Colliery</td>
      <td>England</td>
      <td>Dudley</td>
      <td>Dudley (Un-parished)</td>
      <td>395255.499466851</td>
      <td>283988.832690251</td>
      <td>52.453832</td>
      <td>-2.071245</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-2.07124 52.45383)</td>
    </tr>
    <tr>
      <th>1</th>
      <td>57fe3a562c66dcab3d04f7db</td>
      <td>Victoria Colliery</td>
      <td>England</td>
      <td>Sandwell</td>
      <td>Sandwell (Un-parished)</td>
      <td>400105.421757637</td>
      <td>290519.531861927</td>
      <td>52.512565</td>
      <td>-1.999876</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-1.99988 52.51256)</td>
    </tr>
    <tr>
      <th>2</th>
      <td>57fe3a642c66dcab3d04f7e5</td>
      <td>Lyttleton Colliery</td>
      <td>England</td>
      <td>Sandwell</td>
      <td>Sandwell (Un-parished)</td>
      <td>400022.412780917</td>
      <td>290345.942248252</td>
      <td>52.511004</td>
      <td>-2.001100</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-2.00110 52.51100)</td>
    </tr>
    <tr>
      <th>3</th>
      <td>57fe3a722c66dcab3d04f7eb</td>
      <td>Spon Lane Colliery (Disused)</td>
      <td>England</td>
      <td>Sandwell</td>
      <td>Sandwell (Un-parished)</td>
      <td>400217.558344745</td>
      <td>290229.001480458</td>
      <td>52.509953</td>
      <td>-1.998224</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-1.99822 52.50995)</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5825f9d12c66dcdc11007260</td>
      <td>Blakeley Hall Colliery (Disused)</td>
      <td>England</td>
      <td>Sandwell</td>
      <td>Sandwell (Un-parished)</td>
      <td>399943.744828866</td>
      <td>289538.92252543</td>
      <td>52.503749</td>
      <td>-2.002258</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-2.00226 52.50375)</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>3087</th>
      <td>594faefd2c66dc085a0d76ce</td>
      <td>Newburgh Colliery</td>
      <td>England</td>
      <td>Northumberland</td>
      <td>Togston</td>
      <td>427939.990589279</td>
      <td>601906.602330113</td>
      <td>55.310459</td>
      <td>-1.561376</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-1.56138 55.31046)</td>
    </tr>
    <tr>
      <th>3088</th>
      <td>58938e582c66dc811903b8bd</td>
      <td>Ulgham Grange Colliery (Disused)</td>
      <td>England</td>
      <td>Northumberland</td>
      <td>Ellington</td>
      <td>425143.83493279</td>
      <td>592681.144276922</td>
      <td>55.227714</td>
      <td>-1.606246</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-1.60625 55.22771)</td>
    </tr>
    <tr>
      <th>3089</th>
      <td>594fd6532c66dc085a0d867d</td>
      <td>Brayton Domain Colliery (Pit No. 3)</td>
      <td>England</td>
      <td>Allerdale</td>
      <td>Aspatria</td>
      <td>315962.935197955</td>
      <td>541424.878137047</td>
      <td>54.760702</td>
      <td>-3.307486</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-3.30749 54.76070)</td>
    </tr>
    <tr>
      <th>3090</th>
      <td>58fbaa5c2c66dcf8fa0fdc7a</td>
      <td>Allhallows Colliery</td>
      <td>England</td>
      <td>Allerdale</td>
      <td>Allhallows</td>
      <td>320260.067142663</td>
      <td>542352.390708652</td>
      <td>54.769736</td>
      <td>-3.240980</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-3.24098 54.76974)</td>
    </tr>
    <tr>
      <th>3091</th>
      <td>57f215462c66dca32201ccda</td>
      <td>Iftonrhyn Colliery</td>
      <td>England</td>
      <td>Shropshire</td>
      <td>St Martin's</td>
      <td>332459.033185898</td>
      <td>337375.67239516</td>
      <td>52.929520</td>
      <td>-3.006211</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-3.00621 52.92952)</td>
    </tr>
  </tbody>
</table>
<p>3092 rows × 16 columns</p>
</div>

Once again we have a **geomtry** column. However, now it is called a **POINT** rather than polygon. If we want to plot these points on our map, we again need to check the CRS system (Coordinate Reference System) used. If it dosnt match, we will need to convert. Lets again use the `.crs` function.

```python
cdf.crs
```

    <Geographic 2D CRS: EPSG:4326>
    Name: WGS 84
    Axis Info [ellipsoidal]:
    - Lat[north]: Geodetic latitude (degree)
    - Lon[east]: Geodetic longitude (degree)
    Area of Use:
    - name: World.
    - bounds: (-180.0, -90.0, 180.0, 90.0)
    Datum: World Geodetic System 1984 ensemble
    - Ellipsoid: WGS 84
    - Prime Meridian: Greenwich

So we need to convert to the same EPSG number of 3857. Once again I create a new dataframe to do this as per below, and then preview it.

```python
cdf_wm = cdf.to_crs(epsg=3857)
```

```python
cdf_wm
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>pin_id</th>
      <th>final_text</th>
      <th>nation</th>
      <th>local_auth</th>
      <th>parish</th>
      <th>osgb_east</th>
      <th>osgb_north</th>
      <th>latitude</th>
      <th>longitude</th>
      <th>notes</th>
      <th>field_11</th>
      <th>field_12</th>
      <th>field_13</th>
      <th>field_14</th>
      <th>field_15</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>582454ab2c66dc2d42047bf8</td>
      <td>Witley Colliery</td>
      <td>England</td>
      <td>Dudley</td>
      <td>Dudley (Un-parished)</td>
      <td>395255.499466851</td>
      <td>283988.832690251</td>
      <td>52.453832</td>
      <td>-2.071245</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-230569.907 6882603.812)</td>
    </tr>
    <tr>
      <th>1</th>
      <td>57fe3a562c66dcab3d04f7db</td>
      <td>Victoria Colliery</td>
      <td>England</td>
      <td>Sandwell</td>
      <td>Sandwell (Un-parished)</td>
      <td>400105.421757637</td>
      <td>290519.531861927</td>
      <td>52.512565</td>
      <td>-1.999876</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-222625.234 6893339.631)</td>
    </tr>
    <tr>
      <th>2</th>
      <td>57fe3a642c66dcab3d04f7e5</td>
      <td>Lyttleton Colliery</td>
      <td>England</td>
      <td>Sandwell</td>
      <td>Sandwell (Un-parished)</td>
      <td>400022.412780917</td>
      <td>290345.942248252</td>
      <td>52.511004</td>
      <td>-2.001100</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-222761.387 6893054.187)</td>
    </tr>
    <tr>
      <th>3</th>
      <td>57fe3a722c66dcab3d04f7eb</td>
      <td>Spon Lane Colliery (Disused)</td>
      <td>England</td>
      <td>Sandwell</td>
      <td>Sandwell (Un-parished)</td>
      <td>400217.558344745</td>
      <td>290229.001480458</td>
      <td>52.509953</td>
      <td>-1.998224</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-222441.307 6892861.900)</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5825f9d12c66dcdc11007260</td>
      <td>Blakeley Hall Colliery (Disused)</td>
      <td>England</td>
      <td>Sandwell</td>
      <td>Sandwell (Un-parished)</td>
      <td>399943.744828866</td>
      <td>289538.92252543</td>
      <td>52.503749</td>
      <td>-2.002258</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-222890.374 6891727.288)</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>3087</th>
      <td>594faefd2c66dc085a0d76ce</td>
      <td>Newburgh Colliery</td>
      <td>England</td>
      <td>Northumberland</td>
      <td>Togston</td>
      <td>427939.990589279</td>
      <td>601906.602330113</td>
      <td>55.310459</td>
      <td>-1.561376</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-173811.591 7422354.571)</td>
    </tr>
    <tr>
      <th>3088</th>
      <td>58938e582c66dc811903b8bd</td>
      <td>Ulgham Grange Colliery (Disused)</td>
      <td>England</td>
      <td>Northumberland</td>
      <td>Ellington</td>
      <td>425143.83493279</td>
      <td>592681.144276922</td>
      <td>55.227714</td>
      <td>-1.606246</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-178806.513 7406186.706)</td>
    </tr>
    <tr>
      <th>3089</th>
      <td>594fd6532c66dc085a0d867d</td>
      <td>Brayton Domain Colliery (Pit No. 3)</td>
      <td>England</td>
      <td>Allerdale</td>
      <td>Aspatria</td>
      <td>315962.935197955</td>
      <td>541424.878137047</td>
      <td>54.760702</td>
      <td>-3.307486</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-368187.611 7315561.055)</td>
    </tr>
    <tr>
      <th>3090</th>
      <td>58fbaa5c2c66dcf8fa0fdc7a</td>
      <td>Allhallows Colliery</td>
      <td>England</td>
      <td>Allerdale</td>
      <td>Allhallows</td>
      <td>320260.067142663</td>
      <td>542352.390708652</td>
      <td>54.769736</td>
      <td>-3.240980</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-360784.207 7317304.297)</td>
    </tr>
    <tr>
      <th>3091</th>
      <td>57f215462c66dca32201ccda</td>
      <td>Iftonrhyn Colliery</td>
      <td>England</td>
      <td>Shropshire</td>
      <td>St Martin's</td>
      <td>332459.033185898</td>
      <td>337375.67239516</td>
      <td>52.929520</td>
      <td>-3.006211</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-334649.910 6969971.573)</td>
    </tr>
  </tbody>
</table>
<p>3092 rows × 16 columns</p>
</div>

How do we add this new data on to our existing map? Recall in the first map exercise we created a new axis, **ax1**. This axis provides a canvas on which we can add datapoints. Indeed, we have already found that a dataframe as a `.plot` function. Using this function we can also specify which axis to plot on. Take a look at the new second line in the code snippet below. This looks very much like our previous Matplotlib plot functions. We also still end by using `Contextily` to add a basemap, ensuring we use the correct EPSG code.

```python
# Create a new axis for our bedrock map, using the same options as before.
ax1_new = gdf_wm.plot(figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k", cmap="gist_ncar", legend=True, legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5),"fontsize":7})
# Now plot data from our new colliery dataframr, cdf_wm, specifying the axis to host the datapoints.
cdf_wm.plot(ax=ax1_new, marker='o', color='red', markersize=5)
# Use contextily to add a basemap.
cx.add_basemap(ax1_new, crs='EPSG:3857')
plt.show()
```

![png](output_24_0.png)

Great. Now I want to create a map where only the bedrocl and colliery location overlap. This is too complex to perform manually using a subset search. Fortunately we can join two different GeoDataframes and it will only overlap data where the geomtetry aligns.  We are going to join Pandas dataframes based on time information in a later practical, but we need overlapping geometries.

## Join and Clip GeoPandas dataframes

The `.sjoin` (spatial join) function in GeoPandas is a tool for combining two GeoDataFrames based on their spatial relationship. It's akin to a standard join in Pandas, but instead of joining on keys, it joins based on spatial relationships between the geometries (like points, lines, polygons) in the GeoDataFrames. Take a look at the following code snippet. In the first line we create a new dataframe `joined_df` by combining the bedrock and colliery dataframes, before previewing it.

```python
# Spatial join
joined_df = gpd.sjoin(gdf_wm, cdf_wm)
joined_df
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>LEX</th>
      <th>LEX_D</th>
      <th>LEX_RCS</th>
      <th>RCS</th>
      <th>RCS_X</th>
      <th>RCS_D</th>
      <th>RANK</th>
      <th>BED_EQ</th>
      <th>BED_EQ_D</th>
      <th>MB_EQ</th>
      <th>...</th>
      <th>osgb_east</th>
      <th>osgb_north</th>
      <th>latitude</th>
      <th>longitude</th>
      <th>notes</th>
      <th>field_11</th>
      <th>field_12</th>
      <th>field_13</th>
      <th>field_14</th>
      <th>field_15</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>368</th>
      <td>PSMCM</td>
      <td>PENNINE MIDDLE COAL MEASURES FORMATION AND SOU...</td>
      <td>PSMCM-MSCI</td>
      <td>MSCI</td>
      <td>COAL + FECRTE + FEST + MDST + SDST + SLST</td>
      <td>MUDSTONE, SILTSTONE, SANDSTONE, COAL, IRONSTON...</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>...</td>
      <td>360331.033309896</td>
      <td>398274.335505914</td>
      <td>53.479687</td>
      <td>-2.599200</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
    <tr>
      <th>616</th>
      <td>PSLCM</td>
      <td>PENNINE LOWER COAL MEASURES FORMATION AND SOUT...</td>
      <td>PSLCM-MSCI</td>
      <td>MSCI</td>
      <td>COAL + FECRTE + FEST + MDST + SDST + SLST</td>
      <td>MUDSTONE, SILTSTONE, SANDSTONE, COAL, IRONSTON...</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>...</td>
      <td>329185.103475161</td>
      <td>365875.402043021</td>
      <td>53.185240</td>
      <td>-3.061184</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
    <tr>
      <th>967</th>
      <td>PSMCM</td>
      <td>PENNINE MIDDLE COAL MEASURES FORMATION AND SOU...</td>
      <td>PSMCM-MSCI</td>
      <td>MSCI</td>
      <td>COAL + FECRTE + FEST + MDST + SDST + SLST</td>
      <td>MUDSTONE, SILTSTONE, SANDSTONE, COAL, IRONSTON...</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>...</td>
      <td>421715.135039512</td>
      <td>425173.052322763</td>
      <td>53.722516</td>
      <td>-1.672394</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
    <tr>
      <th>1224</th>
      <td>PSMCM</td>
      <td>PENNINE MIDDLE COAL MEASURES FORMATION AND SOU...</td>
      <td>PSMCM-MSCI</td>
      <td>MSCI</td>
      <td>COAL + FECRTE + FEST + MDST + SDST + SLST</td>
      <td>MUDSTONE, SILTSTONE, SANDSTONE, COAL, IRONSTON...</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>...</td>
      <td>452114.410238619</td>
      <td>342927.810911866</td>
      <td>52.981169</td>
      <td>-1.225255</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
    <tr>
      <th>1298</th>
      <td>WAWK</td>
      <td>WARWICKSHIRE GROUP</td>
      <td>WAWK-MSCI</td>
      <td>MSCI</td>
      <td>COAL + FECRTE + FEST + MDST + SDST + SLST</td>
      <td>MUDSTONE, SILTSTONE, SANDSTONE, COAL, IRONSTON...</td>
      <td>GROUP</td>
      <td>NotAp</td>
      <td>Not Applicable</td>
      <td>NotAp</td>
      <td>...</td>
      <td>389561.795040772</td>
      <td>288291.899290617</td>
      <td>52.492436</td>
      <td>-2.155166</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>11235</th>
      <td>TRIA</td>
      <td>TRIASSIC ROCKS (UNDIFFERENTIATED)</td>
      <td>TRIA-MDSS</td>
      <td>MDSS</td>
      <td>MDST + SDST + SLST</td>
      <td>MUDSTONE, SILTSTONE AND SANDSTONE</td>
      <td>NOT APPLICABLE</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>...</td>
      <td>442727.275177417</td>
      <td>314738.981072574</td>
      <td>52.728613</td>
      <td>-1.368742</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
    <tr>
      <th>11235</th>
      <td>TRIA</td>
      <td>TRIASSIC ROCKS (UNDIFFERENTIATED)</td>
      <td>TRIA-MDSS</td>
      <td>MDSS</td>
      <td>MDST + SDST + SLST</td>
      <td>MUDSTONE, SILTSTONE AND SANDSTONE</td>
      <td>NOT APPLICABLE</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>...</td>
      <td>440202.104439491</td>
      <td>315353.525563364</td>
      <td>52.734330</td>
      <td>-1.406057</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
    <tr>
      <th>11235</th>
      <td>TRIA</td>
      <td>TRIASSIC ROCKS (UNDIFFERENTIATED)</td>
      <td>TRIA-MDSS</td>
      <td>MDSS</td>
      <td>MDST + SDST + SLST</td>
      <td>MUDSTONE, SILTSTONE AND SANDSTONE</td>
      <td>NOT APPLICABLE</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>...</td>
      <td>441856.942464576</td>
      <td>315510.54743131</td>
      <td>52.735616</td>
      <td>-1.381531</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
    <tr>
      <th>11235</th>
      <td>TRIA</td>
      <td>TRIASSIC ROCKS (UNDIFFERENTIATED)</td>
      <td>TRIA-MDSS</td>
      <td>MDSS</td>
      <td>MDST + SDST + SLST</td>
      <td>MUDSTONE, SILTSTONE AND SANDSTONE</td>
      <td>NOT APPLICABLE</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>...</td>
      <td>440862.69551777</td>
      <td>339587.322514203</td>
      <td>52.952116</td>
      <td>-1.393247</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
    <tr>
      <th>11235</th>
      <td>TRIA</td>
      <td>TRIASSIC ROCKS (UNDIFFERENTIATED)</td>
      <td>TRIA-MDSS</td>
      <td>MDSS</td>
      <td>MDST + SDST + SLST</td>
      <td>MUDSTONE, SILTSTONE AND SANDSTONE</td>
      <td>NOT APPLICABLE</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>...</td>
      <td>427419.172879439</td>
      <td>315421.016723801</td>
      <td>52.735733</td>
      <td>-1.595356</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
<p>3081 rows × 72 columns</p>
</div>

We can also use the procedure from the previous practical to list the number of unique bedrock entries in our new dataframe. Specifically, we can apply the function `.value_counts()` to the column in our dataframe to then create a list as follows.

```python
# Analyze distribution
distribution = joined_df['RCS_D'].value_counts()
# Print the distribution list
print(distribution)
```

    RCS_D
    MUDSTONE, SILTSTONE, SANDSTONE, COAL, IRONSTONE AND FERRICRETE          2478
    SILTSTONE AND SANDSTONE WITH SUBORDINATE MUDSTONE                        200
    SEDIMENTARY ROCK CYCLES, CLACKMANNAN GROUP TYPE                          123
    MUDSTONE, SILTSTONE AND SANDSTONE                                         72
    DOLOMITISED LIMESTONE AND DOLOMITE                                        61
    SANDSTONE AND CONGLOMERATE, INTERBEDDED                                   49
    LIMESTONE, ARGILLACEOUS ROCKS AND SUBORDINATE SANDSTONE, INTERBEDDED      34
    LIMESTONE, SANDSTONE, SILTSTONE AND MUDSTONE                              23
    LIMESTONE WITH SUBORDINATE SANDSTONE AND ARGILLACEOUS ROCKS               14
    MAFIC IGNEOUS-ROCK                                                        12
    DOLERITE AND THOLEIITIC BASALT                                             5
    MUDSTONE, SILTSTONE, LIMESTONE AND SANDSTONE                               5
    MAFIC LAVA AND MAFIC TUFF                                                  2
    SANDSTONE, SILTSTONE AND MUDSTONE                                          1
    SEDIMENTARY ROCK CYCLES, STRATHCLYDE GROUP TYPE                            1
    SANDSTONE, LIMESTONE AND ARGILLACEOUS ROCKS                                1
    Name: count, dtype: int64

Now we have created this new dataframe, let's recreate our plot of bedrock with the location of collieries. Our new dataframe however only contains polygons. This is because, by default, in a spatial join the geometries from the 'left' data frame are retained in the output.
The 'right' data frame's geometries do not appear in the resulting data frame; instead, the attributes (columns) of the right data frame are joined to the geometries of the left data frame based on the specified spatial relationship. In some ways we have half of the result we want. But we can use the new polygons in `joined_df` to clip the `cdf_wm` dataframe that contains the points we want. In the following code snippet I do just that.

```python
cdf_wm_clipped=cdf_wm.clip(joined_df)
cdf_wm_clipped
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>pin_id</th>
      <th>final_text</th>
      <th>nation</th>
      <th>local_auth</th>
      <th>parish</th>
      <th>osgb_east</th>
      <th>osgb_north</th>
      <th>latitude</th>
      <th>longitude</th>
      <th>notes</th>
      <th>field_11</th>
      <th>field_12</th>
      <th>field_13</th>
      <th>field_14</th>
      <th>field_15</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2206</th>
      <td>57f20d772c66dca32201cbc2</td>
      <td>Breach Colliery (Disused)</td>
      <td>England</td>
      <td>Mendip</td>
      <td>Leigh-on-Mendip</td>
      <td>369557.074738588</td>
      <td>148833.90749644</td>
      <td>51.237867</td>
      <td>-2.437452</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-271335.924 6663477.961)</td>
    </tr>
    <tr>
      <th>2273</th>
      <td>57f20d922c66dca32201cbc4</td>
      <td>Vobster Colliery (Disused)</td>
      <td>England</td>
      <td>Mendip</td>
      <td>Mells</td>
      <td>370133.34358388</td>
      <td>148879.812170109</td>
      <td>51.238310</td>
      <td>-2.429202</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-270417.485 6663556.786)</td>
    </tr>
    <tr>
      <th>2205</th>
      <td>5854451c2c66dc10b80071de</td>
      <td>Mackintosh Colliery</td>
      <td>England</td>
      <td>Mendip</td>
      <td>Coleford</td>
      <td>369118.209505726</td>
      <td>149774.007120165</td>
      <td>51.246296</td>
      <td>-2.443820</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-272044.758 6664976.843)</td>
    </tr>
    <tr>
      <th>2208</th>
      <td>5878d8022c66dc67e202d8ae</td>
      <td>Mells Colliery (Disused)</td>
      <td>England</td>
      <td>Mendip</td>
      <td>Mells</td>
      <td>371211.786235323</td>
      <td>150103.855439293</td>
      <td>51.249372</td>
      <td>-2.413853</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-268708.879 6665523.846)</td>
    </tr>
    <tr>
      <th>2207</th>
      <td>583ed80e2c66dcd5d001d63b</td>
      <td>Colliery (Disused)</td>
      <td>England</td>
      <td>Mendip</td>
      <td>Buckland Dinham</td>
      <td>374487.042095616</td>
      <td>150764.54446743</td>
      <td>51.255469</td>
      <td>-2.366974</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-263490.380 6666608.296)</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>870</th>
      <td>57fbd1b92c66dcab3d04026d</td>
      <td>West Sleekburn Colliery</td>
      <td>England</td>
      <td>Northumberland</td>
      <td>Northumberland (Un-parished)</td>
      <td>427828.959931872</td>
      <td>584851.531808524</td>
      <td>55.157216</td>
      <td>-1.564801</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-174192.821 7392438.591)</td>
    </tr>
    <tr>
      <th>2133</th>
      <td>57ebdf1d2c66dcd80900237c</td>
      <td>North Seaton Colliery</td>
      <td>England</td>
      <td>Northumberland</td>
      <td>Northumberland (Un-parished)</td>
      <td>429209.711158591</td>
      <td>585830.051981674</td>
      <td>55.165930</td>
      <td>-1.543032</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-171769.529 7394136.528)</td>
    </tr>
    <tr>
      <th>910</th>
      <td>57fbe7ba2c66dcab3d041375</td>
      <td>Woodhorn Colliery</td>
      <td>England</td>
      <td>Northumberland</td>
      <td>Northumberland (Un-parished)</td>
      <td>428982.351972931</td>
      <td>588421.746658331</td>
      <td>55.189231</td>
      <td>-1.546336</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-172137.382 7398678.958)</td>
    </tr>
    <tr>
      <th>3087</th>
      <td>594faefd2c66dc085a0d76ce</td>
      <td>Newburgh Colliery</td>
      <td>England</td>
      <td>Northumberland</td>
      <td>Togston</td>
      <td>427939.990589279</td>
      <td>601906.602330113</td>
      <td>55.310459</td>
      <td>-1.561376</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-173811.591 7422354.571)</td>
    </tr>
    <tr>
      <th>146</th>
      <td>57f160f12c66dca322019839</td>
      <td>Whitburn Colliery</td>
      <td>England</td>
      <td>South Tyneside</td>
      <td>South Tyneside (Un-parished)</td>
      <td>440860.04552191</td>
      <td>563661.266570429</td>
      <td>54.965910</td>
      <td>-1.363335</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>POINT (-151765.720 7355252.773)</td>
    </tr>
  </tbody>
</table>
<p>3081 rows × 16 columns</p>
</div>

Now we can go ahead and create a new map. Notice how only a subset of both polygons and points are now displayed, but both align.

```python
ax4 = joined_df.plot(figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k", cmap="gist_ncar", legend=True, legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5),"fontsize":7})
cdf_wm_clipped.plot(ax=ax4, marker='o', color='red', markersize=5)
cx.add_basemap(ax4, crs='EPSG:3857')
plt.show()
```

![png](output_33_0.png)

To add another useful insight we can also create a histogram of the unique entries in our new dataframe, using the code below.

```python
# Create a histogram
plt.figure(figsize=(10, 6))  # You can adjust the size of the figure
distribution.plot(kind='bar')  # 'bar' for a bar chart (histogram)
plt.title('Distribution of Bedrock Types')
plt.xlabel('Bedrock Type')
plt.ylabel('Frequency')
plt.xticks(rotation=90)  # Rotates the x labels to make them more readable
plt.show()
```

![png](output_35_0.png)

<div class="alert alert-block alert-success">
<b> Exercise 2: Create a map of collieries on mudstone bedrock. <a name="Exercise2"></a>  </b> Repeat the above code demonstration but by joining a bedrock dataframe that only contains data on mudstone deposits. I have chosen the name of a new dataframe for you.
</div>

```python
# -------'INSERT CODE HERE'-------
# Create a subset dataframe with entries that only include 'MUDSTONE'
gdf_wm_ex2 = gdf_wm[gdf_wm["RCS_D"].str.contains('MUDSTONE')]
# Perform spatial join
joined_df_ex2 = gpd.sjoin(gdf_wm_ex2, cdf_wm)
# Create map
ax_ex2 = joined_df_ex2[joined_df_ex2.geom_type == 'Polygon'].plot(figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k", cmap="gist_ncar",legend=True, legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5),"fontsize":7})
cdf_wm.clip(joined_df_ex2).plot(ax=ax_ex2, marker='o', color='red', markersize=5)
cx.add_basemap(ax_ex2, crs='EPSG:3857')
plt.show()
# --------------------------------
```

![png](output_37_0.png)

<div class="alert alert-block alert-success">
<b> Exercise 3. Create a map of colliery location and underlying bedrock in Greater Manchester <a name="Exercise3"></a>
</b>

In this exercise we have been provided with a GeoJSON file that contains the shape of Greater Manchester authorities. We want to use this geometry to clip our existing dataframes on bedrock and colliery locations to create a map of Greater Manchester. I have suggested dataframe names for you in the code snippet below, but you will need to import the relevant code from the examples given above. Please remember that each dataframe should use the same Coordinate Reference System (CRS).

</div>

```python
# -------'INSERT CODE HERE'-------
# Location of the GM authority geometries
file_GM = path+"/data/gmauthorities.geojson"
# Read the .geojson file into a new dataframe
GMdf = gpd.read_file(file_GM)
# Convert to EPSG:3857
GMdf_wm = GMdf.to_crs(epsg=3857)
# Clip the bedrock dataframe
gdf_wm_GM = gdf_wm.clip(GMdf_wm)
# Clip the colliery dataframe
cdf_wm_GM=cdf_wm.clip(GMdf_wm)
# Create a map
ax_ex3 = gdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k", cmap="gist_ncar", legend=True, legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5),"fontsize":7})
cdf_wm_GM.plot(ax=ax_ex3, marker='o', color='red', markersize=8)
#cx.add_basemap(ax3, source="basemap_GM.tif")
cx.add_basemap(ax_ex3, crs='EPSG:3857')
plt.show()
# --------------------------------

```

![png](output_39_0.png)

<div class="alert alert-block alert-success">
<b> Exercise 4. Plot the location of flood risk zones across Greater Manchester <a name="Exercise4"></a>
</b>

In this exercise we have been provided with another Shapefile from the [Environment Agency](https://www.data.gov.uk/dataset/cf494c44-05cd-4060-a029-35937970c9c6/flood-map-for-planning-rivers-and-sea-flood-zone-2). This contains information on areas predicted to have a 0.1% chance of flooding each year. The actual use of this data for planning is somewhat complex, but we have been tasked wth creating two maps for Greater manchester. The first map displays the total extent of the dataset, labelling areas by the predicted cause of flooding (Tidal and Fluvial). The second displays the same inforamtion but only across the Greater Manchester region.

The [different types](https://storymaps.arcgis.com/stories/863d930b86cd427883e2f09be144b679#) of flood relate to the water body which is flooding land areas:
 - Fluvial = river flooding
 - Pluvial = surface water flooding
 - Tidal = coastal flooding and storm surges

We will therefore want to use the Greater Manchester geometry to clip this data provided by the Environment Agency. I have suggested dataframe names for you in the code snippet below, but you will need to import the relevant code from the examples given above. Please remember that each dataframe should use the same Coordinate Reference System (CRS). You will also need to identify which column to use that contains information on the predicted cause.
</div>

```python
# Figure 1 - plot entire dataset

# -------'INSERT CODE HERE'-------
file_flood_risk = path+"/data/EA_floodrisk_level2/Environment_Agency_Flood_Zone_2.shp"
frdf = gpd.read_file(file_flood_risk)
frdf_wm = frdf.to_crs(epsg=3857)
ax_ex4 = frdf_wm.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k", cmap="winter", legend=True)
cx.add_basemap(ax_ex4, crs='EPSG:3857', zoom=10)
plt.show()
# --------------------------------
```

![png](output_41_0.png)

```python
# Figure 2 - plot the dataset covering only the Greater Manchester region

# -------'INSERT CODE HERE'-------
frdf_wm_GM = frdf_wm.clip(GMdf_wm)
ax_ex4b = frdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k", cmap="winter", legend=True)
cx.add_basemap(ax_ex4b, crs='EPSG:3857', zoom=12)
plt.show()
# --------------------------------

```

![png](output_42_0.png)

# 3) Calculating distances between points and polygons  <a name="Part3">

In GeoPandas, the calculation of distances between points and polygons is carried out using the ```Shapely``` library, which GeoPandas relies on for geometric operations. This process involves measuring the shortest distance between the point geometry and the nearest part of the polygon geometry. Specifically, for each point, the distance is calculated to the closest boundary or vertex of the polygon. If a point lies inside a polygon, the distance to the polygon is considered zero.

We can see how useful this may be. For example, calculating distances to environmental hazards or inferring accesibility to green space.  GeoPandas makes this process straightforward through methods like ```.distance()```. When you call this method on a series containing point geometries and pass a polygon geometry as an argument, it returns a new Series with the distance from each point to the polygon. Similarly, if applied on a polygon GeoSeries with a point as an argument, it calculates the distances from each polygon to the point. This method is particularly useful in spatial analysis for determining proximity, defining buffer zones, or analyzing spatial relationships between different geometric entities.

It's important to note that the distance is calculated in the coordinate system of the geometries, so for accurate distance measurements, especially over larger geographic areas, it's advisable to use a coordinate system appropriate for distance measurement, like a projected coordinate system we referred to earlier. As if by magic, we have been using a CRS (EPSG:3857) that is based on metres. The following table outlines many of the EPSG codes that use metres. 'Geographic' means the system uses latitude and longitude degrees, while 'Projected' systems use linear units like meters or feet. In geographic coordinate systems (like EPSG:4326), distances are calculated along the surface of a spheroid, making them more complex to compute, especially over large distances. In contrast, projected systems use a flat, two-dimensional plane, making distance calculations straightforward but potentially less accurate over large areas.

| EPSG Code | Reference System Name                               | Distance Type       |
|-----------|----------------------------------------------------|---------------------|
| 4326      | WGS 84                                              | Geographic          |
| 3857      | WGS 84 / Pseudo-Mercator                            | Projected (Meters)  |
| 32633     | WGS 84 / UTM zone 33N                               | Projected (Meters)  |
| 27700     | OSGB36 / British National Grid                      | Projected (Meters)  |
| 3395      | WGS 84 / World Mercator                             | Projected (Meters)  |
| 3577      | GDA94 / Australian Albers                           | Projected (Meters)  |
| 25832     | ETRS89 / UTM zone 32N                               | Projected (Meters)  |
| 26713     | NAD27 / UTM zone 13N                                | Projected (Meters)  |
| 54004     | World Sinusoidal                                    | Projected (Meters)  |
| 6933      | WGS 84 / NSIDC EASE-Grid 2.0 Global                 | Projected (Meters)  |

We can now start to build an example of how distance capabilities are useful in GeoPandas. In the following we load another ```.shp``` file that contains information on the location of [electricity substations](https://www.nationalgrid.com/stories/energy-explained/what-is-a-substation#:~:text=Substations%20contain%20equipment%20that%20help,network%20failures%20or%20power%20cuts.) from the [UK National Grid website](https://www.nationalgrid.com/electricity-transmission/network-and-infrastructure/network-route-maps). We are first going to produce a map constrained to Greater Manchester. In the following code snippet after loading the file I once again make sure this information is based on the same CRS we have been using up to this point. You may also notice I apply the function ```.centroid``` to create a new dataframe. This is solely for the purpose of wanting to use single points to represent the substation location rather than complec geometries. A preview of the new dataframe confirms we are left with point geometries.

```python
file_substation = path+"/data/Substations_10Dec23/Substations.shp"
ssdf = gpd.read_file(file_substation)
ssdf_wm = ssdf.to_crs(epsg=3857)
# copy GeoDataFrame
ssdf_wm_copy = ssdf_wm.copy()
# change geometry
ssdf_wm_copy['geometry'] = ssdf_wm_copy['geometry'].centroid
ssdf_wm_copy
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>SUBSTATION</th>
      <th>OPERATING_</th>
      <th>ACTION_DTT</th>
      <th>STATUS</th>
      <th>Substation</th>
      <th>OWNER_FLAG</th>
      <th>GDO_GID</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>DAMC4</td>
      <td>400kV</td>
      <td>2020-06-09</td>
      <td>C</td>
      <td>DAMHEAD CREEK 400KV S/S</td>
      <td>Y</td>
      <td>10051888.0</td>
      <td>POINT (66647.027 6696701.062)</td>
    </tr>
    <tr>
      <th>1</th>
      <td>MONF2</td>
      <td>275kV</td>
      <td>2020-06-09</td>
      <td>C</td>
      <td>MONK FRYSTON 275KV S/S</td>
      <td>Y</td>
      <td>10051889.0</td>
      <td>POINT (-140956.880 7124278.600)</td>
    </tr>
    <tr>
      <th>2</th>
      <td>MONF2</td>
      <td>275kV</td>
      <td>2020-06-09</td>
      <td>C</td>
      <td>MONK FRYSTON 275KV S/S</td>
      <td>Y</td>
      <td>10051890.0</td>
      <td>POINT (-141035.267 7124006.987)</td>
    </tr>
    <tr>
      <th>3</th>
      <td>ACTL8</td>
      <td>25kV</td>
      <td>2020-06-09</td>
      <td>C</td>
      <td>ACTON LANE 22KV S/S</td>
      <td>Y</td>
      <td>10051891.0</td>
      <td>POINT (-28846.000 6716313.185)</td>
    </tr>
    <tr>
      <th>4</th>
      <td>ACTL8</td>
      <td>25kV</td>
      <td>2020-06-09</td>
      <td>C</td>
      <td>ACTON LANE 22KV S/S</td>
      <td>Y</td>
      <td>10051892.0</td>
      <td>POINT (-28717.915 6716144.820)</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>542</th>
      <td>BIGG4</td>
      <td>400kV</td>
      <td>2023-06-02</td>
      <td>P</td>
      <td>BIGGLESWADE 400KV S/S</td>
      <td>Y</td>
      <td>556.0</td>
      <td>POINT (-25494.226 6814717.819)</td>
    </tr>
    <tr>
      <th>543</th>
      <td>UXBM1</td>
      <td>132kV</td>
      <td>2023-06-02</td>
      <td>P</td>
      <td>UXBRIDGE MOOR 132KV S/S</td>
      <td>Y</td>
      <td>558.0</td>
      <td>POINT (-55779.192 6717682.110)</td>
    </tr>
    <tr>
      <th>544</th>
      <td>UXBM4</td>
      <td>400kV</td>
      <td>2023-06-02</td>
      <td>P</td>
      <td>UXBRIDGE MOOR 400KV S/S</td>
      <td>Y</td>
      <td>558.0</td>
      <td>POINT (-55759.390 6717624.007)</td>
    </tr>
    <tr>
      <th>545</th>
      <td>OCKH3</td>
      <td>0kV</td>
      <td>2023-07-24</td>
      <td>P</td>
      <td>OCKER HILL 33KV S/S</td>
      <td>Y</td>
      <td>560.0</td>
      <td>POINT (-226036.535 6898624.215)</td>
    </tr>
    <tr>
      <th>546</th>
      <td>SUND3A</td>
      <td>kV</td>
      <td>2023-10-24</td>
      <td>P</td>
      <td>SUNDON 33KV GRID PARK S/S</td>
      <td>Y</td>
      <td>561.0</td>
      <td>POINT (-55809.503 6789009.730)</td>
    </tr>
  </tbody>
</table>
<p>547 rows × 8 columns</p>
</div>

In the next code snippet we clip our susbstation dataframe ```ssdf_wm_copy``` to the Greater Manchester boundaries provided by the dataframe ```GMdf_wm```. We then combine a plot of our existing floodrisk geometries and the new points that represent the location of substations; both supplemented by another basemap provided by the ```contextily``` module.

```python
ssdf_wm_GM = ssdf_wm_copy.clip(GMdf_wm)
frdf_wm_GM = frdf_wm.clip(GMdf_wm)
ax_ex4c = frdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k", cmap="winter", legend=True)
ssdf_wm_GM.plot(ax=ax_ex4c, marker='o', color='red', markersize=18)
cx.add_basemap(ax_ex4c, crs='EPSG:3857', zoom=12)
plt.show()
```

![png](output_46_0.png)

## Adding a distance buffer

These maps already allow us to beter understand potential risk from flooding. We are inferring that substations are subject to a level of risk from flooding, which has attracted a number of [studies and government projects](https://climate-adapt.eea.europa.eu/en/metadata/case-studies/flood-defence-framework-for-national-grid-substations-in-united-kingdom) as the frequency of extreeme weather events increase.

To take this one step further we would like to account for the distance from our substations to the predicted flooding areas. We have been working with EPSG:3857 Coordinate Reference System which is based in metres, but how can we interact with this metric?

The first method we can use is ```.buffer```. The ```.buffer()``` method in GeoPandas is used to create a buffer zone around the geometries in a GeoSeries or GeoDataFrame. This method is particularly useful in spatial analysis, where you might want to create a zone of a specific distance around a point, line, or polygon. More specifically, in our example we can create a 1KM radius around our substation points and then plot these on the map. The .buffer() method generates a new geometric object that represents an area covered within a given distance from the original geometry. For example, if applied to a point, it will create a circle (or an approximate circle in geographic coordinate systems) around the point. If applied to a line, it creates a strip of specified width along the line.  The distance used in the .buffer() method is in the units of the GeoDataFrame's CRS. For instance, if the CRS is in latitude and longitude (like EPSG:4326), the distance is in degrees, which is not intuitive for distance measurements.

In the following code snippet we use the ```.buffer``` method on the ```ssdf_wm_GM``` dataframe which creates a new dataframe, ```risk_zone```. We pass a value of 1000 to represent 1Km. We then preview the new dataframe to confirm we have created a new set of polygons.

```python
# get circle with 1 km radius
risk_zone = ssdf_wm_GM.buffer(1000)
risk_zone
```

    389    POLYGON ((-235993.437 7060050.402, -235998.252...
    174    POLYGON ((-236252.384 7060180.038, -236257.200...
    393    POLYGON ((-252393.258 7061128.836, -252398.073...
    407    POLYGON ((-252264.842 7061456.955, -252269.657...
    16     POLYGON ((-226575.062 7074470.583, -226579.877...
    492    POLYGON ((-226749.512 7074538.453, -226754.328...
    387    POLYGON ((-263837.663 7062136.511, -263842.478...
    209    POLYGON ((-266396.592 7063771.965, -266401.408...
    60     POLYGON ((-267126.029 7064046.204, -267130.844...
    59     POLYGON ((-266946.724 7064170.013, -266951.539...
    137    POLYGON ((-226234.027 7074841.808, -226238.843...
    320    POLYGON ((-240256.171 7081407.501, -240260.986...
    31     POLYGON ((-261428.444 7083081.174, -261433.259...
    62     POLYGON ((-245623.786 7098831.565, -245628.601...
    219    POLYGON ((-245782.596 7098900.465, -245787.412...
    223    POLYGON ((-261551.736 7083024.974, -261556.551...
    225    POLYGON ((-261648.759 7083405.206, -261653.575...
    dtype: geometry

Now in the following code snippet we once again plot our flood risk geometries and substation points but now we add our new buffer geometries. In this example I specify a strange looking ```color="#ff000033"``` to create a transparent circle so we can better see the 1km distance zone.

```python
ax_ex4d = frdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k", cmap="winter", legend=True)
ssdf_wm_GM.plot(ax=ax_ex4d, marker='o', color='red', markersize=18)
risk_zone.plot(ax=ax_ex4d, color="#ff000033")
cx.add_basemap(ax_ex4d, crs='EPSG:3857', zoom=12)
plt.show()
```

![png](output_50_0.png)

## Calculating distances between points and polygons

To take this one step further we should be able to calculate and access distances between our points and flood risk polygons. This will allow us to determine which points are in the flood risk zone (distance of 0) or within a user specified tolerance. There are a number of processes taking place in the following code snippet. The aim is to iterate through each substation and calculate the distance to all flood risk areas.

<div class="alert alert-block alert-info">

 - Create a ```for loop``` to cycle through each substation in the dataframe ```ssdf_wm_GM```. :
 > ```for index, row in ssdf_wm_GM.iterrows():``` - the ```.iterrows()``` method of a GeoPandas dataframe returns a unique list of indices and the row content from the dataframe.
 > We confirm the name of the current substation by printing ```row['Substation']```.
 > distances = frdf_wm_GM.geometry.distance(row.geometry) - This is the key command that returns a list of ```distances```.
 >>  ```frdf_wm_GM.geometry.distance```.  The method ```.geometry.distance(row.geometry)``` allows us to calculate the distance from the polygons held within the dataframe ```frdf_wm_GM``` with the information held in ```(row.geometry)```.

At every loop we print the distances to the screen.

</div>

```python
for index, row in ssdf_wm_GM.iterrows():
    # Select one station in particular
    print(row['Substation'])
    # Measure distance from release to each station
    distances = frdf_wm_GM.geometry.distance(row.geometry)
    print(distances)
```

    BREDBURY 275KV S/S
    995     15316.356074
    1230    13617.006048
    1891    20862.606691
    1892    19995.599135
    1917    20062.968048
                ...
    7333    50787.963067
    7392    49320.222082
    7317    50234.510976
    7318    50395.827465
    7319    50398.403868
    Length: 921, dtype: float64
    BREDBURY 132KV S/S
    995     15404.481203
    1230    13572.098602
    1891    20676.904964
    1892    19814.480061
    1917    19879.535906
                ...
    7333    50569.697445
    7392    49218.967747
    7317    50013.264530
    7318    50175.197156
    7319    50177.848613
    Length: 921, dtype: float64
    SOUTH MANCHESTER 275KV S/S
    995     17739.808930
    1230    14397.325286
    1891     9706.535941
    1892     9477.737272
    1917     9371.364333
                ...
    7333    45964.552707
    7392    52579.460351
    7317    45181.359857
    7318    45389.689110
    7319    45398.569819
    Length: 921, dtype: float64
    SOUTH MANCHESTER 132KV S/S
    995     17955.259888
    1230    14609.895788
    1891    10057.711176
    1892     9824.869895
    1917     9719.263450
                ...
    7333    45645.683152
    7392    52227.490944
    7317    44864.539844
    7318    45072.396657
    7319    45081.218692
    Length: 921, dtype: float64
    STALYBRIDGE 275KV S/S
    995     31845.347383
    1230    30830.264965
    1891    36472.285032
    1892    35742.121578
    1917    35752.438408
                ...
    7333    43413.481752
    7392    34897.127586
    7317    43179.906229
    7318    43278.581098
    7319    43274.350998
    Length: 921, dtype: float64
    STALYBRIDGE 25KV S/S
    995     31843.549174
    1230    30788.054361
    1891    36378.021836
    1892    35650.671645
    1917    35659.980170
                ...
    7333    43247.295367
    7392    34808.722600
    7317    43011.751846
    7318    43110.797564
    7319    43106.605612
    Length: 921, dtype: float64
    DAINES 400KV S/S
    995     26217.391331
    1230    23213.447524
    1891    13455.802457
    1892    14070.256525
    1917    13891.916874
                ...
    7333    45652.610711
    7392    57358.905511
    7317    44741.030997
    7318    44977.667397
    7319    44990.673204
    Length: 921, dtype: float64
    CARRINGTON 275KV S/S
    995     29241.142189
    1230    26248.567586
    1891    16373.845864
    1892    17027.630128
    1917    16849.441856
                ...
    7333    44609.269162
    7392    57564.574387
    7317    43674.323511
    7318    43915.723485
    7319    43929.658537
    Length: 921, dtype: float64
    CARRINGTON 132KV S/S
    995     29987.121332
    1230    27005.902922
    1891    17074.689038
    1892    17742.882458
    1917    17564.854480
                ...
    7333    44530.584983
    7392    57802.030095
    7317    43589.864321
    7318    43832.404333
    7319    43846.585784
    Length: 921, dtype: float64
    CARRINGTON 400KV S/S
    995     29919.866861
    1230    26927.387873
    1891    17040.380394
    1892    17699.284892
    1917    17521.142140
                ...
    7333    44364.052988
    7392    57593.316116
    7317    43424.365280
    7318    43666.701994
    7319    43680.838657
    Length: 921, dtype: float64
    STALYBRIDGE 400KV S/S
    995     32317.710373
    1230    31329.396177
    1891    36970.190978
    1892    36241.304423
    1917    36251.181287
                ...
    7333    43363.426767
    7392    34572.764223
    7317    43141.589638
    7318    43238.004299
    7319    43233.544026
    Length: 921, dtype: float64
    WHITEGATE 275KV S/S
    995     35536.994313
    1230    32476.254953
    1891    33126.056239
    1892    32717.404159
    1917    32644.097047
                ...
    7333    29709.953027
    7392    29244.884271
    7317    29290.133086
    7318    29424.311061
    7319    29423.800462
    Length: 921, dtype: float64
    KEARSLEY 275KV S/S
    995     41353.382589
    1230    38001.844687
    1891    31872.413719
    1892    32059.004834
    1917    31904.998689
                ...
    7333    24671.239449
    7392    40086.013656
    7317    23737.938875
    7318    23978.835775
    7319    23992.676807
    Length: 921, dtype: float64
    ROCHDALE 132KV S/S
    995     52905.443139
    1230    49672.691584
    1891    47963.438910
    1892    47781.868228
    1917    47672.829234
                ...
    7333    12665.501682
    7392    17916.828598
    7317    12607.718189
    7318    12677.281092
    7319    12668.038741
    Length: 921, dtype: float64
    ROCHDALE 275KV SITE
    995     52981.904136
    1230    49746.173694
    1891    47999.637659
    1892    47821.251367
    1917    47711.775466
                ...
    7333    12500.422131
    7392    18007.601653
    7317    12438.957415
    7318    12508.768169
    7319    12499.753833
    Length: 921, dtype: float64
    KEARSLEY 400KV S/S
    995     41357.665264
    1230    38007.592128
    1891    31841.773884
    1892    32032.098751
    1917    31877.720464
                ...
    7333    24756.222446
    7392    40216.241500
    7317    23821.436418
    7318    24062.635634
    7319    24076.539310
    Length: 921, dtype: float64
    KEARSLEY 132KV GSP S/S
    995     41741.450010
    1230    38390.468803
    1891    32233.739785
    1892    32424.437030
    1917    32270.035603
                ...
    7333    24412.995106
    7392    40044.568233
    7317    23475.609859
    7318    23717.327751
    7319    23731.341128
    Length: 921, dtype: float64

Rather than retain all the distances from each substation, I want to only retain the minimum distance. This way I can determine if any substations are in risk zones (distance = 0) and keep a record of the non-zero distance if they are not. In the following code snippet we initialise an empty list and, at every stage of our loop, store the minimum distance (in KM) from every substation.

```python
min_distances=[]
for index, row in ssdf_wm_GM.iterrows():
    # Select one station in particular
    print(row['Substation'])
    # Measure distance from polygons to each station
    distances = frdf_wm_GM.geometry.distance(row.geometry)
    # Print the minimum distance
    print(distances.min())
    # Update min_distances list to account for the distance in km
    min_distances.append(distances.min()/1000.0)

# Add this new list into our existing GeoPandas dataframe as a new column named 'min distance to flood'
ssdf_wm_GM['min distance to flood']=min_distances
```

    BREDBURY 275KV S/S
    212.68743051913467
    BREDBURY 132KV S/S
    251.23069364215402
    SOUTH MANCHESTER 275KV S/S
    0.0
    SOUTH MANCHESTER 132KV S/S
    0.0
    STALYBRIDGE 275KV S/S
    0.0
    STALYBRIDGE 25KV S/S
    141.54007718982592
    DAINES 400KV S/S
    1588.087455581972
    CARRINGTON 275KV S/S
    201.78059738173124
    CARRINGTON 132KV S/S
    0.0
    CARRINGTON 400KV S/S
    0.0
    STALYBRIDGE 400KV S/S
    0.0
    WHITEGATE 275KV S/S
    1295.0350784971433
    KEARSLEY 275KV S/S
    136.3071588961682
    ROCHDALE 132KV S/S
    429.4027782829802
    ROCHDALE 275KV SITE
    269.9180509202209
    KEARSLEY 400KV S/S
    267.88594221561283
    KEARSLEY 132KV GSP S/S
    96.46211101706979

    /Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/geopandas/geodataframe.py:1543: SettingWithCopyWarning:
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead

    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      super().__setitem__(key, value)

What am I going to do with this information? We can see from the preview we have some substations within the flood zone. Before I create another map Id like to change the colour of the substation depending on whether it is less than 1Km from a flood risk or not. In the code snippet below I create another column in our dataframe that holds the colour according to this criteria. Do not worry about the ```lambda`` function. This is a very efficient, but not very readable, way of performing a calculation dependent on conditions.

```python
 # Create a new column for colors
ssdf_wm_GM['color'] = ssdf_wm_GM['min distance to flood'].apply(lambda x: 'aqua' if x > 1 else 'red')
```

    /Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/geopandas/geodataframe.py:1543: SettingWithCopyWarning:
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead

    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      super().__setitem__(key, value)

Now we have our new colour column, in the following I recreate our mapn but now pass a color argument, ```color=ssdf_wm_GM['color']```, that will colour our substations accordingly. In the map that is created, a red point represents an area at risk (under our defintion) and an aqua point not at risk.

```python
ax_ex4e = frdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k", cmap="winter", legend=True)
ssdf_wm_GM.plot(ax=ax_ex4e, marker='o', color=ssdf_wm_GM['color'], markersize=18)
risk_zone.plot(ax=ax_ex4e, color="#ff000033")
cx.add_basemap(ax_ex4e, alpha=0.5, crs='EPSG:3857', zoom=12)
plt.show()
```

![png](output_58_0.png)

One last addition before the final exercise. We have already clipped our dataframes using the geometries of the Greater Manchester region in ```GMdf_wm```. However, it would also be nice to see administrative boundaries provided within that dataframe. If we preview the dataframe we see the different metropolitan districts:

```python
GMdf_wm
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>LGDNAME</th>
      <th>AREA</th>
      <th>LGDCode</th>
      <th>OBJECTID</th>
      <th>NAME</th>
      <th>AREA_CODE</th>
      <th>DESCRIPTIO</th>
      <th>FILE_NAME</th>
      <th>NUMBER</th>
      <th>NUMBER0</th>
      <th>...</th>
      <th>UNIT_ID</th>
      <th>CODE</th>
      <th>HECTARES</th>
      <th>TYPE_CODE</th>
      <th>DESCRIPT0</th>
      <th>TYPE_COD0</th>
      <th>DESCRIPT1</th>
      <th>X</th>
      <th>Y</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>Trafford District (B)</td>
      <td>MTD</td>
      <td>Metropolitan District</td>
      <td>TRAFFORD_DISTRICT_(B)</td>
      <td>10</td>
      <td>55</td>
      <td>...</td>
      <td>18786</td>
      <td>E08000009</td>
      <td>10604.476</td>
      <td>AA</td>
      <td>CIVIL ADMINISTRATION AREA</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>MULTIPOLYGON (((-270251.496 7055260.349, -2702...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>Manchester District (B)</td>
      <td>MTD</td>
      <td>Metropolitan District</td>
      <td>MANCHESTER_DISTRICT_(B)</td>
      <td>4</td>
      <td>70</td>
      <td>...</td>
      <td>18821</td>
      <td>E08000003</td>
      <td>11564.826</td>
      <td>AA</td>
      <td>CIVIL ADMINISTRATION AREA</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>MULTIPOLYGON (((-254514.620 7052821.304, -2544...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>Wigan District (B)</td>
      <td>MTD</td>
      <td>Metropolitan District</td>
      <td>WIGAN_DISTRICT_(B)</td>
      <td>15</td>
      <td>60</td>
      <td>...</td>
      <td>18868</td>
      <td>E08000010</td>
      <td>18817.091</td>
      <td>AA</td>
      <td>CIVIL ADMINISTRATION AREA</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>MULTIPOLYGON (((-290781.985 7072493.189, -2908...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>Oldham District (B)</td>
      <td>MTD</td>
      <td>Metropolitan District</td>
      <td>OLDHAM_DISTRICT_(B)</td>
      <td>8</td>
      <td>48</td>
      <td>...</td>
      <td>18690</td>
      <td>E08000004</td>
      <td>14234.507</td>
      <td>AA</td>
      <td>CIVIL ADMINISTRATION AREA</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>MULTIPOLYGON (((-223693.395 7097907.620, -2236...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>Bolton District (B)</td>
      <td>MTD</td>
      <td>Metropolitan District</td>
      <td>BOLTON_DISTRICT_(B)</td>
      <td>13</td>
      <td>50</td>
      <td>...</td>
      <td>18832</td>
      <td>E08000001</td>
      <td>13979.210</td>
      <td>AA</td>
      <td>CIVIL ADMINISTRATION AREA</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>MULTIPOLYGON (((-262089.546 7080934.550, -2620...</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>Rochdale District (B)</td>
      <td>MTD</td>
      <td>Metropolitan District</td>
      <td>ROCHDALE_DISTRICT_(B)</td>
      <td>4</td>
      <td>44</td>
      <td>...</td>
      <td>18825</td>
      <td>E08000005</td>
      <td>15812.803</td>
      <td>AA</td>
      <td>CIVIL ADMINISTRATION AREA</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>MULTIPOLYGON (((-226077.399 7100246.328, -2260...</td>
    </tr>
    <tr>
      <th>6</th>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>Salford District (B)</td>
      <td>MTD</td>
      <td>Metropolitan District</td>
      <td>SALFORD_DISTRICT_(B)</td>
      <td>6</td>
      <td>44</td>
      <td>...</td>
      <td>18805</td>
      <td>E08000006</td>
      <td>9719.732</td>
      <td>AA</td>
      <td>CIVIL ADMINISTRATION AREA</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>MULTIPOLYGON (((-274703.144 7064323.487, -2747...</td>
    </tr>
    <tr>
      <th>7</th>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>Bury District (B)</td>
      <td>MTD</td>
      <td>Metropolitan District</td>
      <td>BURY_DISTRICT_(B)</td>
      <td>9</td>
      <td>38</td>
      <td>...</td>
      <td>18846</td>
      <td>E08000002</td>
      <td>9946.009</td>
      <td>AA</td>
      <td>CIVIL ADMINISTRATION AREA</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>MULTIPOLYGON (((-258854.474 7105168.935, -2588...</td>
    </tr>
    <tr>
      <th>8</th>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>Stockport District (B)</td>
      <td>MTD</td>
      <td>Metropolitan District</td>
      <td>STOCKPORT_DISTRICT_(B)</td>
      <td>12</td>
      <td>50</td>
      <td>...</td>
      <td>18757</td>
      <td>E08000007</td>
      <td>12604.032</td>
      <td>AA</td>
      <td>CIVIL ADMINISTRATION AREA</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>MULTIPOLYGON (((-232970.653 7064341.363, -2329...</td>
    </tr>
    <tr>
      <th>9</th>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>Tameside District (B)</td>
      <td>MTD</td>
      <td>Metropolitan District</td>
      <td>TAMESIDE_DISTRICT_(B)</td>
      <td>15</td>
      <td>44</td>
      <td>...</td>
      <td>18700</td>
      <td>E08000008</td>
      <td>10315.421</td>
      <td>AA</td>
      <td>CIVIL ADMINISTRATION AREA</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
      <td>MULTIPOLYGON (((-232970.653 7064341.363, -2329...</td>
    </tr>
  </tbody>
</table>
<p>10 rows × 21 columns</p>
</div>

We could plot this directly using the ```.boundary.plot``` method as per the figure below.

```python
GMdf_wm.boundary.plot(edgecolor='blue')
plt.show()
```

    <Axes: >

![png](output_62_1.png)

However we want to add this to our risk map. To do that, we repeat this same command but attach it to the axis created for our flood risk map.

```python
ax_ex4f = frdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k", cmap="winter", legend=True)
ssdf_wm_GM.plot(ax=ax_ex4f, marker='o', color=ssdf_wm_GM['color'], markersize=18)
risk_zone.plot(ax=ax_ex4f, color="#ff000033")
GMdf_wm.boundary.plot(ax=ax_ex4f, edgecolor='blue')
cx.add_basemap(ax_ex4f, alpha=0.5, crs='EPSG:3857', zoom=12)
plt.show()
```

![png](output_64_0.png)

<div class="alert alert-block alert-success">
<b> Exercise 5. Create a map of flooding and substation risk for the Stockport District <a name="Exercise5"></a>
</b>

In this exercise we want to use the polygon that represents the Stockport District in the dataframe ```GMdf_wm``` to clip our existing dataframes and produce a plot that focuses solely on this region.

```python
# -------'INSERT CODE HERE'-------
# Create new flood risk dataframe for Stockport
Stock_frdf_wm_GM = frdf_wm_GM.clip(GMdf_wm[GMdf_wm['NAME']=='Stockport District (B)'])
# Create new substation dataframe for Stockport
Stock_ssdf_wm_GM = ssdf_wm_GM.clip(GMdf_wm[GMdf_wm['NAME']=='Stockport District (B)'])
# Create new buffer zone
risk_zone = Stock_ssdf_wm_GM.buffer(1000)
# Create new map
ax_ex5 = Stock_frdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k", cmap="winter", legend=True)
Stock_ssdf_wm_GM.plot(ax=ax_ex5, marker='o', color='red', markersize=12)
risk_zone.plot(ax=ax_ex5, color="#ff000033")
GMdf_wm.clip(GMdf_wm[GMdf_wm['NAME']=='Stockport District (B)']).boundary.plot(ax=ax_ex5, edgecolor='blue')
cx.add_basemap(ax_ex5, alpha=0.5, crs='EPSG:3857', zoom=12)
plt.show()
# --------------------------------
```

![png](output_66_0.png)

## ⚙️ What We Did

> 🟦 **In this practical, we:**
>
> - Introduced **Geographic Information Systems (GIS)** concepts using Python
> - Used **GeoPandas** to work with spatial (map-based) data
> - Learned the difference between:
>   - **Vector data** (points, lines, polygons)
>   - **Raster data** (gridded spatial data, discussed conceptually)
> - Loaded and worked with **geospatial file formats**, including:
>   - Shapefiles
>   - GeoJSON files
> - Visualised spatial data on maps to show real-world locations
> - Combined multiple spatial datasets to explore how different features relate
> - Focused on real-world examples such as:
>   - Bedrock geology
>   - Collieries and quarries
>   - Flood risk zones
>
> 🧠 *The focus was on learning how spatial data is represented, combined, and visualised, and how GIS-style questions can be explored using Python.*

---

## 📝 Exercises

> 🟦 **Exercise 1: Mapping limestone bedrock**
>
> - Filtered geological data to select only **limestone bedrock**
> - Created a map showing where limestone deposits are located
>
> 🧠 *Goal: practise selecting spatial features and visualising them on a map.*

---

> 🟦 **Exercise 2: Mapping collieries on mudstone**
>
> - Selected colliery locations from a spatial dataset
> - Filtered geological data to include only **mudstone bedrock**
> - Produced a map showing where collieries sit relative to mudstone geology
>
> 🧠 *Goal: explore relationships between industrial sites and underlying geology.*

---

> 🟦 **Exercise 3: Collieries and bedrock in Greater Manchester**
>
> - Loaded a GeoJSON file defining the **Greater Manchester** boundary
> - Combined bedrock and colliery datasets
> - Created a focused map showing both datasets within the same region
>
> 🧠 *Goal: learn how multiple spatial layers can be combined to answer location-based questions.*

---

> 🟦 **Exercise 4: Flood risk zones in Greater Manchester**
>
> - Loaded flood risk zone data from a spatial dataset
> - Visualised flood risk areas across Greater Manchester
>
> 🧠 *Goal: understand how GIS data is used to represent environmental risk.*

---

> 🟦 **Exercise 5: Flooding and substation risk in Stockport**
>
> - Selected the polygon representing the **Stockport district**
> - Filtered flood risk data to this specific area
> - Combined flood risk and infrastructure data
> - Created a map highlighting potential **risk to substations**
>
> 🧠 *Goal: see how spatial filtering helps focus analysis on a specific real-world problem.*

```python

```
