---
title: "Lecture 2 - Spatial Data and Data Management"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 2/Lecture 2 - Spatial Data and Data Management.pdf"
type: pdf
---

# Spatial data and data management

#### Lecture 2 content:

- ➢ the characteristics of spatial data

- ➢ object and field views and surface models

- ➢ understand map scale and cartographic abstraction

- ➢ map projections and projected coordinate systems

- ➢ how spatial data are represented, structured and organised using computers

- ➢ understand differences between vector and raster

representations

1

## Nature of spatial data

- ➢ Spatial data are usually ‘observational’ rather than ‘experimental’.

- ➢ Spatial data capture the complexity of the real world in finite form through a particular process of conceptualisation and representation.

- ➢ Spatial data record locations according to a particular georeferencing system.

2

## Conceptualisation – Object view

##### ➢The object view

➢populated by individual objects.

- ➢point, line and area objects, or features.

➢exactly located, welldefined boundaries and countable.

3

## Conceptualisation – Field view

##### ➢ The field view

➢ covered by continuous surfaces in which the attribute values can be defined at every location

4

## Surface Models: DEM and DTM

- ➢ **Digital Elevation Model (DEM)**

   - A 3D representation of a terrain surface.

   - ‘bare-earth’ elevation model, meaning it is free of vegetation, man-made structures and other non-terrain objects.

   - DEMs are usually either raster (grid of squares), or vector-based triangular irregular network (TIN) data.

- ➢ **Digital Terrain Model (DTM)**

Is a DEM augmented by other surface features including information about terrain shape (slope, curvature) and drainage structure.

_DTM and DEM are often used interchangeably because they are similar_

5

## Digital Terrain Model

Light = high elevations, Dark = low elevations

6

## Topography (hillshade)

7

## Relief and topography

8

## 3D visualisation

9

## Draping layers on a 3D surface

10

## Draping layers on a 3D surface

11

## Triangulated irregular network (TIN)

- ➢ Vector-based model for surface morphology

- ➢ Surface is modelled as contiguous layer of triangles.

➢ Each triangle is a plane with constant gradient. ➢ Each point in TIN has 3D coordinates (x,y,z) as verticies (nodes).

OS Terrain 5m TIN – triangulated irregular networks uses triangles which relate to features more accurately than a grid. https://www.ordnancesurvey.co.uk/documents/osterrain-5-user-guide.pdf

12

## DEM using TIN

13

## Map scale

The Ratio of distance on the map or image to the corresponding distance on the ground.

Smaller the map scale:

➢ the larger the ratio

- ➢ less accurate

- ➢ more abstract

14

## Large and small map scales

➢ The smaller the map scale, the fewer geographical features and less detail about these geographical features can be captured and represented.

1:3,000,000 1:800,000 _Small scale = large area Less detail_

_Large scale_ 1:40,000 _= small area More detail_

15

## Generalisation

- ➢ Cartographical generalisation or abstraction is the process of transforming reality to a map.

- ➢ **Selection** chooses and retains the most

   - important geographical features.

- ➢ **Simplification** means removing complexity

- ➢ **Exaggeration** is used to retain or emphasise important characteristics.

- ➢ **Combination** merges similar features.

- ➢ **Displacement** moves objects to keep them distinguishable.

- ➢ **Classification** group features by attributes

16

## The shape of the Earth

geoid = an equipotential surface of the Earth’s gravitational field= mean sea level reference spheroid = smooth surface model of Earth’s geoid

_a - b = 21.4 km_

17

## Major Earth’s spheroids

WGS = World Geodetic System GRS = Geodetic Reference System (1980)

18

## Datum accounts for local variations

Geographical coordinate values depend upon the chosen reference spheroid and datum

19

## Geographic coordinate system

Parallels

###### Prime meridian

Meridians

20

## ‘Normal’ map projections

<!-- Start of picture text -->
conic<br>azimuthal<br><!-- End of picture text -->

cylindrical conic azimuthal

21

## Cylindrical map projections

_Standard parallels_

_Secant lines cut the sphere_

22

## Secant Normal Mercator projection

_Increasing distortion No distortion Increasing distortion No distortion Increasing distortion_

23

### Some countries are smaller than you think!

Mercator projection:

https://geospatialworld.net/blogs/maps-that-showwhy-some-countries-are-not-as-big-as-they-look/

- ➢ preserves shapes and directions

- ➢ distorts area and distances (apart from equator)

24

### Universal Transverse Mercator (UTM) system

25

### Vector data model is based on object view

- ➢ Based on the object view of geographical space.

- ➢ The vector data model typically stores spatial data as feature classes.

- ➢ A feature class is a collection of geographical features of the same geometric type (point, line and polygon) with the same set of attributes. Examples:

   - a **point** feature class may represent meteorological stations as

   - points with observed values of meteorological variables;

   - a **line** feature class may represent streams with a set of stream attributes (length, elevation and gradient);

   - a **polygon** feature class may represent land parcels with land use

   - types.

26

## Vector data model coordinates

27

### Raster data model is based on field view

28

## Elements of a raster

North

Cell or pixel depth: **greyscale:** 8-bit = 2<sup>8</sup> -1 = 0-255 shades (black to white) **colour:** 8-bit RGB channels = 16.7 million colours

29

## Raster representations with different cell sizes

Increasing cell size = lower resolution and loss of detail

30

## Homework and Resources

➢ Read Chapter 2 of course textbook: Spatial Data and Management

➢ Take the quiz to test your basic understanding (on Canvas)

###### **Further resources**

Introduction to Spatial Data | Esri Training Web Course https://www.esri.com/training/catalog/5dd4485b6cd66f196f beddad/introduction-to-spatial-data/

Read the text, don’t attempt the ArcGIS Pro exercises

31

## OCR 补充（原文中无文字层的页面）

_(以下内容由图片 OCR 识别得到，原文件该处无可提取文字。**识别质量低**——原件疑为手写或图件，文字大多不可靠，仅作线索，务必对照原件。)_

### Page 7

Topography (hillshade)

### Page 8

Relief and topography

### Page 9

3D visualisation

### Page 13

DEM using TIN

498.889 -
MB 433.333 -
MM 367.778 -

302.222 -

236.667 -
Me 7.111 -

105.556 -

40 - 105.556

564.444
498.889
433,333
367.778
302.222
236.667
171.111

13
