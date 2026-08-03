---
title: "Lecture_3_Spatial data input and manipulation_handout"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 3/Lecture_3_Spatial data input and manipulation_handout.pdf"
type: pdf
---

## Spatial data input and manipulation

#### Lecture 3 content:

➢ Different spatial data capture techniques. ➢ The fundamentals of a GNSS.

➢ Spatial data formats and transfer. ➢ Basics of spatial data editing. ➢ Assessing spatial data quality. ➢ Some of the main errors in spatial data.

## Spatial data capture

##### ➢ Spatial data capture is the process of generating new digital spatial data.

➢ It involves direct measurement or analogue-todigital conversion.

## Vector data capture

##### ➢ keyboard entry

➢ digitising

- ➢ field surveying

- ➢ photogrammetry

##### ➢ LiDAR (light detection and ranging)

## Keyboard entry

➢ Involves obtaining the coordinates of point features from maps, field data or other source documents, and typing them into the GIS.

- ➢ Point features are also called _XY events._

- ➢ Used when the number of point features is small.

## Manual digitising

➢ Manually tracing along boundaries of geographical features from a map or image, while recording the coordinates of the points selected to approximate the boundary or shape of each feature.

- ➢ Digitizing table and a puck.

## On-Screen digitising

- ➢ On-screen digitising using scanned paper maps as digital images and then tracing the features on a computer screen.

- ➢ Limited by the resolution of the scanned images and may not capture fine details as accurately as manual digitizing.

<!-- Start of picture text -->
Digitising involves accuracy not density of points<br><!-- End of picture text -->

_Digitising involves accuracy not density of points_

# Automatic digitising

- ➢ Automatic digitizing converts raster images into vector data using raster-to-vector conversion.

- ➢ This method is highly efficient for handling large datasets.

- ➢ . Part of a wider push toward automated digital mapping

# Digitising data in GIS

_https://aigeo360.com/digitization-in-gis/_

## Field surveying

- ➢ Collect spatial data  through direct measurements in the field.

- ➢ Traditionally surveying methods are used

➢ More recently, total stations and GNSS.

## Total station surveying

https://cpe.leica-geosystems.com/ca/blog/post/what-is-a-total-station-how-it-works.html

https://www.clevelandbrothers.com/job-site-layoutbase-station-total-station/

### Global Navigation Satellite System (GNSS)

- ➢ Provides accurate measurement of a position almost anywhere on the surface of the Earth.

- ➢ Hand-held GNSS receivers allow data collectors to walk or drive _x z_

- around to collect ( , _y_ , ) coordinates at sample points.

- ➢ GPS (USA), GLONASS Russia), Galileo (Europe) and BeiDou (China) are three main GNSS systems that are currently operational.

<!-- Start of picture text -->
s<br><!-- End of picture text -->

_https://vangarde-industries.com/products/gps-tracking-system_

### GNSS constellations with global coverage

https://eos-gnss.com/knowledge-base/gps-overview-1-what-is-gps-and-gnss-positioning

### Main features of a GNSS

- ➢ GPS satellites orbit 20,200km above the Earth in a period of twelve hours in six orbital planes.

- ➢ This configuration ensures that at least **four** satellites (the minimum number required for accurate measurements) are always potentially visible anywhere on Earth

- ➢ Each satellite emits signals in 2-3 frequency bands as radio waves, long wavelength electromagnetic radiation which is able to penetrate the atmosphere. At least one of the bands is reserved for military use.

- ➢ The low power means arriving signals are not much different from background noise level.

## Smartphone GNSS

**Alt** = altitude above WGS84 ellipsoid. **Alt (MSL)** = geoid-based Earth Gravitational Model (e.g. EGM96 which defines sea level). **TTFF** = Time To First Fix on satellites.

**E H/V Acc** = Estimated Horizontal and Vertical accuracy.

**L1/L5** radio bands (L5 civilian high precision) _GPStest app for Android downloaded from Google Play_

<!-- Start of picture text -->
Smartphone GNSS<br>Sky map of visible GNSS constellations with<br>connected satellites in bold outline.<br>C/N0  =  ratio of signal power to noise<br>power density, is an important parameter<br>for measuring the quality of the received<br>signal.<br>Good Conditions:  Values in the 35–45 dB-<br>Hz range are common (satellite elevation,<br>obstructions, antenna, band).<br>GPStest app downloaded from Google Play<br>App Store.<br><!-- End of picture text -->

## Photogrammetry

➢ _x z_ Photogrammetry measures ( , _y_ , ) coordinates of objects using overlapping pairs of aerial photographs (stereo-pair) taken from different points of view.

https://wingtra.com/drone-photogrammetry-vs-lidar/

https://www.aerotas.com/overlap-flight-pattern

## Laser scanning (LiDAR)

- ➢ _x z_ LiDAR produces ( , _y_ , ) coordinates for multiple discrete points, called mass points or point clouds.

- ➢ Photogrammetry and LiDAR can achieve a vertical accuracy of 10-15 cm and horizontal accuracy of 50-100 cm.

## Raster data capture

➢ Remotely sensed images, including satellite images and aerial photographs. Four main types visible, infrared, multispectral, and hyperspectral.

_Visible (greyscale or colour bands)_

_Visible and infrared (colour bands or continuous)_

## Crowdsourcing

- ➢ Collect spatial data by soliciting contributions from the community or general public.

- ➢ Involve the use of Internet-enabled and locationaware mobile devices to gather location-specific information.

- ➢ Disadvantages: possibly skewed data, lack of ownership or confidentiality, loss of expertise.

# Spatial data transfer

- ➢ The process of converting or translating existing digital spatial data and importing them into a GIS.

- ➢ Import existing spatial data from external sources.

- ➢ May be in different data formats.

- ➢ Read directly or translated into a suitable format.

# Digital spatial data formats

## Feature Manipulation Engine

➢ ArcGIS Pro incorporates FME technology for spatial data transfer.

- ➢ Supports >300 formats of spatial and non-spatial data.

e.g. various GIS, rasters, databases, 3D, XML, and point cloud (LiDAR) data.

### Spatial data transformation and editing

##### ➢ Data structure conversion (raster-vector conversion).

➢ Geometric transformation – rubber sheeting.

- ➢ Line simplification.

- ➢ Edge matching.

## Data structure conversion

###### Rasterisation and loss of information

<!-- Start of picture text -->
Rasterisation and loss of information<br><!-- End of picture text -->

Vectorisation and distortion

## Spatial transformations

###### **Rubber sheeting** – correcting geometric distortions

**Similarity  transformation** – translate, rotate or scale – preserves shape (angles do not change)

## Spatial transformations

**Affine transformation** scales, skews, rotates and translates – preserve parallelism (length and angles may change).

_Requires a minimum of 3 control points_

**Edge matching** – match features across data layers.

## Line simplification (weeding)

Removes insignificant bends and redundant points or vertices from a line or a polygon while preserving its essential shape.

# Spatial data errors

#### Some common sources of errors in GIS data:

- ➢ Data formatting errors

   - ➢ scale, coordinate projection, raster conversion etc

#### ➢ Cartographical generalisation errors

- ➢ Location errors

- ➢ Topological errors

- ➢ Attribute errors

# Topological errors

Topology errors arise when spatial features don't connect, intersect or align correctly, according to the spatial rules in a GIS.

Most are common when manually digitising a scanned map (except knots).

## Attribute errors

➢ Attribute data may contain observational or measurement errors, data entry errors or be simply out of date.

➢ Editing includes adding, deleting, or updating attributes associated with features and their values.

## Spatial data quality

➢ Spatial data may contain inherent errors.

➢ Their quality must be compatible with their intended applications.

➢ _Spatial data quality_ - the level of accuracy, precision, completeness, consistency and timeliness of the data that makes them appropriate for a particular use.

## Attribute errors and accuracy

Map data

Reference data

How many pixels have been assigned to the incorrect land use and land cover type?

## Cross-tabulation or error matrix

###### _Reference data_

_Map data_

||Grassland|Forest|Marsh|Rows Total|
|---|---|---|---|---|
|Grassland|28|14|15|57|
|Forest|1|15|5|21|
|Marsh|1|1|20|22|
|Columns Total|30|30|40|100|

Grassland = (28/30) * 100 = 93% Forest = (15/30) * 100 = 50% Marsh = (20/40) * 100 = 50% Overall Accuracy = (28 + 15+ 20) = 63%

## Positional accuracy

- ➢ How closely the coordinate descriptions of features represented in the data compare with their true location.

- ➢ Measured using the Root Mean Square Error (RMSE): xyz = true location, x’y’z’ = encoded position; n = number of data values.

- ➢ RMSE has the same units as the x,y,z measurements (e.g. metres, deg-C. etc). An RMSE = 0 means there is no error in the accuracy.

## Data quality

- ➢ **Precision** : The recorded level of detail.

- ➢ **Consistency** : The lack of apparent contradictions between datasets or within a dataset.

- ➢ **Completeness** : The extent and range of a dataset with regard to completeness of coverage, classification and verification.

## Metadata

- ➢ The data about data.

➢ Describe the content, quality, condition and other characteristics of a dataset.

➢ Lineage - history of both the source data and the processing steps used to produce the spatial dataset.

- ➢ International metadata standards.

# Homework and Resources

- ➢ Read Chapter 3 of course textbook: Spatial Data Input and Manipulation

➢ Take the quiz to test your basic understanding (on Canvas)

###### **Further resources**

ESRI training: Getting Started with Imagery and Remote Sensing (component 1 only; 45 mins)

https://www.esri.com/training/catalog/634f16c15030f204ae8 e30f4/getting-started-with-imagery-and-remote-sensing/

37

## OCR 补充（原文中无文字层的页面）

_(以下内容由图片 OCR 识别得到，原文件该处无可提取文字；识别可能有误，请对照原件。)_

### Page 21

Digital spatial data formats

Vector Raster
ESRI ArcInfo Coverage ESRI GRID
ESRI ArcInfo E00 (ArcInfo Interchange Format) DTED (Digital Terrain Elevation Data)
ESRI ArcView Shapefile ERDAS IMG (IMAGINE)
MapInfo MIF (Map Interchange Format) BMP (Windows Bitmap)
USGS DLG (Digital Line Graphs) TIFF (Tagged Image File Format)
AutoCAD DXF (Data Exchange Format) GeoTIFF
AutoCAD DWG (Drawing) GIF (Graphics Interchange Format)
CGM (Computer Graphics Metafile, ISO) JPEG (Joint Photographic Experts Group)
Microstation DGN (Microstation drawing file PNG (Portable Network Graphics)
format)
SDTS (Spatial Data Transfer Standard , US) USGS DEM
NTF (National Transfer Format, UK) ECW (Enhanced Compressed Wavelet)

TIGER (Topologically Integrated Geographic
Encoding and Referencing System, US Bureau
of Census)

DIME (Dual Independent Map Encoding, US
Bureau of Census)

VPF (Vector Product Format, National Imagery
and Mapping Agency, US)

EML (Keyhole Markup Language, Google)
WFS (Web Feature Service, Open Geospatial
Consortium)

NetCDF (Network Common Data Form, Unidata)
8-457 (Intemational Hydrographic Organization)
