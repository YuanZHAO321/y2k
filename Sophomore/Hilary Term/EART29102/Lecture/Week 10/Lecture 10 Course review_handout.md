---
title: "Lecture 10 Course review_handout"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 10/Lecture 10 Course review_handout.pdf"
type: pdf
---

# Course Overview - Aims

1. Introduce and develop understanding of the principles and applications of geospatial techniques.

2. Show how different types of geospatial data can be collected (including remote sensing techniques). 3. Develop skills required to deal effectively with geospatial data through real world examples.

4. To be able to add, store, analyse and present geospatial data using a Geographical information systems (GIS). 5. Develop proficiency in using the GIS software ArcGIS Pro.

## Theory

<!-- Start of picture text -->
Intro to GIS Data  Analysis  Remote  Terrain  Cartography 3D<br>input &  and  sensing analysis visualisation<br>handling statistics<br><!-- End of picture text -->

## Practical

<!-- Start of picture text -->
Air pollution<br>Wind<br>Geology<br>Arc GIS Pro turbines<br>maps<br>Data input  Flood<br>Mineral<br>and analysis hazards<br>resources<br>Solar<br>mapping<br><!-- End of picture text -->

## GIS functional components

## Concept views of geographical space

_The object view - point, line & area objects (vector)._

_The field view - continuous surfaces (raster)._

<!-- Start of picture text -->
A<br><!-- End of picture text -->

<!-- Start of picture text -->
B<br><!-- End of picture text -->

_Trees as discrete objects_

_Tree height as continuous surface_

## Vector data

|**Advantages**|**Disadvantages**|
|---|---|
|Data can be<br>represented in their<br>original resolution<br>without<br>generalization.|More complex data<br>structure.|
|Requires less disk<br>storage space.|Inefficient for<br>remotely sensed data.|
|Topological<br>relationships are<br>readily maintained.|Some spatial analysis<br>procedures are<br>complex and process<br>intensive.|
|Graphical output<br>resembles hand-<br>drawn maps.|Overlaying multiple<br>vector maps is often<br>time consuming.|

## Raster data

|**Advantages**|**Disadvantages**|
|---|---|
|Simple data structure.|Requires greater disk<br>storage space.|
|Efficient for remotely<br>sensed or scanned data<br>(continuous data).|Depending on pixel size,<br>graphical output may be<br>less pleasing.|
|Simple spatial analysis<br>procedures|Projection transformations<br>are more difficult.|
||Difficult to represent<br>topological relationships.|

## Spatial data models

###### **Vector data capture**

Keyboard entry Digitising Field surveying Photogrammetry LiDAR Crowdsourcing

**_Conversion_ Raster data capture** _rasterisation_ Remote sensing including satellite images and aerial _vectorisation_ photographs Crowdsourcing

### Map projections and coordinates systems

- ➢ Data are located on the Earth’s surface using georeferences.

- ➢ The Earth’s shape is modelled as a sphere (oblate spheroid).

- ➢ Spherical reference model e.g. WGS84 – often enhanced using an equipotential surface of the Earth’s gravitational field at mean sea level (the geoid).

- ➢ Local datum takes account of regional variations  e.g. NAD27, OSGB36.

- ➢ A geographical coordinate system defines a position on the Earth’s surface in spherical coordinates (e.g. latitude and longitude).

- ➢ A projected coordinate system transforms the Earth’s spherical surface to a 2D flat surface (maps, computer screen) and coordinates (x, y) are “flat” on a grid system e.g. UTM, British National Grid.

#### Global Navigation Satellite System (GNSS)

- ➢ A GNSS consists of a constellation of satellites orbiting the Earth.

- ➢ For global coverage, it is estimated that a constellation requires 18 to 30 satellites.

- ➢ GPS (USA), GLONASS (Russia), Galileo (Europe) and BeiDou (China) are four main GNSS systems that are currently operational.

- ➢ Position of an object is its latitude (distance from the equator), longitude (distance from the Greenwich meridian in the UK) and elevation above (or below) mean sea level.

- ➢ Four “visible” satellites are required for positioning with mm-scale accuracy possible.

- ➢ Hand-held GNSS receivers allow coordinates to be obtained at sample points.

## Spatial analysis and modelling

## Methods of spatial analysis

➢ **Spatial query:** filtering and selecting data from a geodatabase based on attributes and location. ➢ **Spatial operations:** a type of spatial query class that includes operations such as intersection, containment, and distance calculations for objects in a given region or point.

➢ **Spatial interpolation:** estimates unknown values at specific locations based on known values from surrounding points.

## Spatial interpolation methods

- ➢ Inverse distance weight (IDW) – deterministic (interpolated value only).

➢ Kriging – geostatistical (interpolated value and probability).

<!-- Start of picture text -->
IDW<br><!-- End of picture text -->

<!-- Start of picture text -->
Kriging<br><!-- End of picture text -->

## Spatial Autocorrelation

- ➢ Measure of the similarity (correlation) between nearby observations.

- ➢ Spatial pattern is clustered (close proximity), dispersed (spread out), or random.

Negative ----- spatial autocorrelation ----- Positive

- ➢ Null hypothesis = spatial distribution is random.

- ➢ Alternate hypotheses = spatial clustered or dispersed.

## Spatial statistics

- ➢ **.** _Nearest neighbour_ – measures spatial autocorrelation using locations

- ➢ _Moran’s I_ (local or global)  - measures spatial auotocorrelation using feature values and their locations (a single statistic). Identifies clusters and outliers.

- ➢ _Getis Ord Gi*_ - hot-spot analysis identifies statistically significant clustering of high values (hot spots) and low values (cold spots).

- ➢ _Kernel density estimation_ – shows heat maps as a smooth density surface across an area showing concentrations of locations or feature values).

## Remote sensing data

- ➢ Techniques for collecting environmental data from a distance without coming into direct contact with the objects of interest.

- ➢ Record the magnitude of electromagnetic energy flux that is reflected or emitted from the objects on the Earth’s surface or within the atmosphere (normally imagery).

- ➢ Airplanes, satellites, and UAVs equipped with sensors.

Landsat and Sentinel 2 satellites

Lidar, Radar (and Sonar)

https://www.earthdata.nasa.gov/learn/backgrounders/remote-sensing

## Spectral reflectance

_visible infrared_

## Digital multispectral images

~~. Spectral band width or~~ **~~spectral resolution~~**

<!-- Start of picture text -->
Pixel depth or<br>radiometric resolution<br>8-bit = 2 8  -1 = 0 -255.<br><!-- End of picture text -->

Pixel size or **spatial resolution**

## Sentinel spectral bands

|aerosols, bathymetry|
|---|
|colour images|
|vegetation health|
|agriculture and<br>forestry|
|vegetation, biomass,<br>plant health|
|water vapour<br>cirrus clouds|
|burnt areas, moisture<br>content|

## Terrain analysis

##### ➢ Contours, spot heights, DEM (raster) and TIN (vector).

_different ways of representing the same continuous surface at the same scale and extent_

https://gistbok.ucgis.org/bok-topics/triangular-irregular-network-tin-models00

### Primary and secondary terrain attributes

➢ Primary attributes are calculated directly from a DEM include elevation, slope, aspect, plan and profile curvature.

➢ Secondary attributes are computed from two or more primary attributes e.g. solar radiation, moisture index, sediment transport index, etc. ➢ Used to quantify the movement and distribution of water in the landscape, and the amount of solar radiation received at the surface.

## Applications of terrain analysis

###### _Catchment hydrology_

_Line of sight and viewsheds Solar radiation mapping_

### Cartographic editing and generalisation

|**Editing**|**Generalisation (cartographic abstraction)**|
|---|---|
|Rubber sheeting – remove geometric<br>distortions.|Selection – retain important features.|
|Transformation – rotate, scale, skew or<br>translate features.|Simplification – remove complexity.|
|Edge matching – feature matching across<br>layers.|Exaggeration – emphasise important<br>features.|
|Line simplification – simplify while retaining<br>shape.|Combination – merge similar features.|
|Error corrections - overshoot, unclosed<br>polygon, etc.|Displacement – move to make<br>distinguishable.|
|Reshaping individual features.|Classification – group similar features.|
|_Large scale_<br>_= small area_|_Small scale_<br>_= large area_|

<!-- Start of picture text -->
Reshaping individual features. Classification – group similar features.<br>Large scale Small scale<br>= small area = large area<br><!-- End of picture text -->

Mackaness et al (2017).. https://doi.org/10.1002/9 781118786352.wbieg101 <u>5</u>

## Map types

General purpose maps

- provide geographical information for reference purposes

   - topographic maps - comprehensive reference information about a region

   - base map - a foundation for superimposing additional layers of information

Thematic maps

- map the spatial distribution of a single attribute or variable or the relationship among several variables

_dot, isoline, choropleth, proportional, graduated, etc._

## Map design

**Selection:** selecting the geographical area, geographical features, map scale, projection, data variables, etc. **Classification:** grouping and categorising data

**Symbolisation:** selecting symbols and visual variables to represent data in a logical way

**Layout design:** organising disparate cartographic elements coherently on a page

## Map elements

## Animated mapping

##### ➢ Animated mapping uses animation to show changes over **time, space** or **attributes** .

- ➢ Animations can be temporal and non-temporal.

_animation showing the positions of Antarctic icebergs through time_

## 2.5D versus 3D mapping

- ➢ Geological map draped over a DEM.

- ➢ The map is a surface existing in 3D space. But a point on this surface can still be described using only x and y coordinates (a 2 D surface).

- ➢ Third dimension represents a single attribute value e.g. elevation above sea level.

- ➢ Referred to as 2.5D maps.

## True 3D

<!-- Start of picture text -->
Geological model<br><!-- End of picture text -->

Digital twins

- ➢ Volume is integral in geospatial 3D.

- ➢ True 3D geospatial data requires three coordinates (x, y, z) because it represents volume, not just surface position.

- ➢ Without z, it is not possible to locate where inside the volume something is.

## Digital space

<!-- Start of picture text -->
PIXELS<br><!-- End of picture text -->

The smallest unit of information in a 2D raster image. Each pixel has an x, y location.

<!-- Start of picture text -->
VOXELS<br>z<br>y<br>x<br>Esri<br><!-- End of picture text -->

A 3 dimensional pixel used to display 3D images.

A voxel = a small cube defined by x, y, z extents.

## EART29102 Exam

- ➢ Online exam under controlled conditions i.e. is invigilated and not able to refer to notes, books, web resources or use AI.

- ➢ Exam is 70% of the final mark for the course

- ➢ 50 questions: majority are multiple choice, some are multiple answer.

- ➢ Multiple choice questions are similar in style to the lecture quiz questions.

- ➢ Use the weekly quizzes as practice.

- ➢ Take your time and read each question carefully.

## Example multiple answer question

Which TWO of the following are forms of geometric corrections applied to satellite multispectral images? _(2 marks)_

A. Removal of geometric distortions caused by sensor-Earth geometry variations. B. Georeferencing an image to a particular projected map coordinate system. C. Correcting an image for sensor response properties and viewing geometry. D. Correcting an image for atmospheric effects and scene illumination. E. Restoring an image to accurately represent the radiance measured by the sensor.

_Answer:_ A and B are geometric corrections. The others are radiometric corrections. These corrections are applied before any image enhancement (e.g. band combinations) are applied.

|No attempt|Select both|Select one|Select any two,|Select any two|
|---|---|---|---|---|
||correct answers|correct answer|one correct, one|incorrect|
|||only|incorrect|answers|
|0|2|1|0|0|

## OCR 补充（原文中无文字层的页面）

_(以下内容由图片 OCR 识别得到，原文件该处无可提取文字；识别可能有误，请对照原件。)_

### Page 4

GIS functional components

Application Programming

User Interface Interface
. Interface f
Spatial Data } | Spatial Data || Spatial Data [| Spatial Data | Too/s5
Input Manipulation Analysis Output
Data

management

### Page 27

Map elements

Title

v
Households with Very High Income in Melbourne
by Local Government Areas in 2006

North arrow

Map body

Legend
inset

Scale bar

Credits Neatline Other text information

### Page 33

ONE HOUR THIRTY MINUTES
THE UNIVERSITY OF MANCHESTER

GEOSPATIAL TECHNIQUES

08 June 2026

14:00 — 15:30

Instructions for candidates

Answer ALL questions in the online exam.

This is a closed book exam.

The use of Al software is prohibited.

There are 80 marks available on this exam. The number of marks for each question is
shown and may be used as a guide to how much time you should spend on each.

Some questions require you to select more than one correct answer from a list.

You gain marks for each correct answer selected.
You lose marks for each incorrect answer selected.
You do not lose marks for answers you do not select.
The minimum score for each question is 0.

Answers to the online exam MUST be submitted at the end of the exam.

Additional permitted materials

The use of calculators is NOT permitted for this exam.
