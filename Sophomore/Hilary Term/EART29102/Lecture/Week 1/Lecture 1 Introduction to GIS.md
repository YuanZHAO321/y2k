---
title: "Lecture 1 Introduction to GIS"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 1/Lecture 1 Introduction to GIS.pdf"
type: pdf
---

# EART29102 Geospatial Techniques

Lecture 1: Course Overview and Introduction _Teaching staff:_

Ray Burgess (co-ordinator) Rufus Brunt Peter Grinrod (Natural History Museum) Ben Esse (practical classes)

1

# Lecture outline

➢ What this course aims to achieve and how it is structured.

➢ The teaching and learning methods, feedback and assessment.

- ➢ What is a GIS and what is it used for?

- ➢ What are geospatial data?

- ➢ How data are represented (modelled) as vector and raster structures?

➢ A brief introduction to GIS software - ArcGIS Pro (practical).

2

# Course Overview - Aims

1. Introduce and develop understanding of the principles and applications of geospatial techniques.

2. Show how different types of geospatial data can be collected (including remote sensing techniques). 3. Develop skills required to deal effectively with geospatial data in earth and environmental sciences through real world examples.

4. To be able to add, store, analyse and present geospatial data using a Geographical information systems (GIS). 5. Develop proficiency in using the GIS software ArcGIS Pro.

3

# Intended Learning Outcomes (ILO’s)

ILO 1: Understand what a GIS is and how it is structured. ILO2: Define how spatial reference systems, datums, and projections are used in recording locations. ILO3: Illustrate how geospatial data, at a wide range of scales, can be used to help solve scientific and societal problems. ILO4: Choose appropriate geospatial techniques to solve a given scientific problem. ILO5: Be competent in applying geospatial analysis and visualisation using ArcGIS Pro software.

4

# Feedback and assessment

#### **Formative**

- ➢ Weekly short answer and multiple-choice quizzes based on lecture content (ILOs 1-3).

- ➢ Weekly feedback on ArcGIS Pro examples and workshops to support progress of case studies (ILOs 4-5)

#### ➢ **Summative**

- ➢ Canvas test of 50 questions to demonstrate knowledge and understanding of GIS relevant to earth and environmental applications (summer exam period) – ILO’s 1,2,3 (70%).

- ➢ ArcGIS Pro software project on selected case study to demonstrate competence of ArcGIS Pro and analysis of spatial data (30%). Submission at end of week 11 (30<sup>th</sup> April, 2026) (ILO’s 4,5).

5

# Teaching methods

- ➢ 1 hr lecture and 2 hr practical class each week.

- ➢ The lectures will provide the background theory and context for the practical exercises.

- ➢ The module will use ESRI ArcGIS Pro software in practical classes.

- ➢ Supported by on-line videos (mainly ESRI training videos) and core textbook.

6

# Introduction to GIS

7

## Geographic Information System (GIS)

_Geographic Information System (GIS)_ is a computer-based system for capture, management, storage, organization and analysis of spatially-referenced data, and the output of spatially-referenced information.

_Data_ are a collection of related facts; the basic elements of information.

_Information_ is data that have been processed to be useful. It provides answers to questions, used in decision-making.

8

# What does a GIS do?

- ➢ Capture data: add data from many sources to a GIS and create data from scratch.

- ➢ Store data: store and manage information about the real world in ways that make sense for an application.

- ➢ Query data: ask complex questions about features based on their attributes or their location and get quick results.

- ➢ Analyse data: can integrate multiple datasets to find features that meet specific criteria and create information useful for problem solving.

- ➢ Display data: display features based on their attributes, a powerful feature of any GIS.

- ➢ Present data: create and distribute high-quality maps, graphs, and reports to present analysis results in a compelling way to an audience.

# Features of spatial data

- ➢ Spatial data are related using a coordinate system which defines spherical or planimetric coordinates, elevation, orientation etc.

- ➢ Observations and measurements are made on geographically distributed features such as plants, wildlife animals, rivers, etc. Each of these spatial objects is an entity that can be described by its attribute or property.

➢ Attributes or properties may include observable and/or measurable characteristics, e.g. Tree is observation, latitude and longitude define its location, while elevation, aspect, slope, solar radiation, soil type, etc are attributes specific to that location.

11

# GIS functional components

<!-- Start of picture text -->
6<br><!-- End of picture text -->

<!-- Start of picture text -->
1<br><!-- End of picture text -->

<!-- Start of picture text -->
3<br><!-- End of picture text -->

<!-- Start of picture text -->
4<br><!-- End of picture text -->

<!-- Start of picture text -->
5<br><!-- End of picture text -->

<!-- Start of picture text -->
2<br><!-- End of picture text -->

12

# Spatial data analysis component

➢ A collection of tools for exploring patterns, associations and interactions of environmental phenomena as well as evidence of their changes through time and over space.

➢ Include spatial query, geometric measurement, buffering and proximity measurement, overlay analysis, surface analysis, network analysis, image analysis and spatial statistics.

13

## Buffering and proximity measurement

- ➢Functions used to calculate distances around (buffer) and from (proximity) a feature or features.

e.g. use a 100 m buffer around rivers or calculate distances from a river to assess flood risk.

_Buildings in red are in 100m buffer zone of rivers._

14

# Geometric functions

➢Calculate properties such as length, perimeter, area, shape, orientation, centroid and distances.

- ➢Useful for landscape metrics, analysing landscape fragmentation and characterising landscape structures.

<!-- Start of picture text -->
Distance of track<br><!-- End of picture text -->

Distance of track Perimeter and area

<!-- Start of picture text -->
Perimeter and area<br><!-- End of picture text -->

15

# Layers and Attribute tables

16

# Overlay analysis functions

- ➢ Stacking of layers of different themes based on common geography.

- ➢ Useful to identify spatial associations (e.g. overlaps) for optimal site selection or suitability modelling.

<!-- Start of picture text -->
Land cover<br><!-- End of picture text -->

<!-- Start of picture text -->
Soil type<br><!-- End of picture text -->

<!-- Start of picture text -->
Base map<br><!-- End of picture text -->

17

# GIS uses layers of data

- ➢ GIS often combines information from different _layers._

- ➢ _._ Layers form a stack with multiple datasets found in x,y,z location

**USGS National Map** provides access to base geospatial information to describe the landscape of the United States and its territories.

- Comprises 8 layers at 1:24,000 scale - On-line National Map viewer https://apps.nationalmap.gov/viewer/ https://www.usgs.gov/programs/nationalgeospatial-program/national-map

18

# Mineral deposit exploration

- ➢ Background map

- ➢ Aerial photos/satellite images

- ➢ Environmental data

- ➢ Geological field data

- ➢ Geophysical data

- ➢ Geochemical data

_Arvanitidis et al 2012_

19

# Spatial data models

The most common representation of spatial data that measures the landscape is using discrete data (vector model) and continuous data (raster models).

**Vector data capture** Keyboard entry Digitising Field surveying Photogrammetry LiDAR

**Raster data capture**

Remote sensing including satellite images and aerial photographs

20

# Vector data model

- ➢Features that have definite boundaries and identities and a specific shape using points, lines, and polygons.

- ➢Useful for storing data that have discrete boundaries, such as groundwater wells , streams, and lakes.

21

# Raster model data

➢Represent geographic features by dividing them into a discrete grid of cells (pixels).

➢Useful for storing data that vary continuously, e.g. aerial photographs, satellite images, a surface of humidity, or digital elevation model (DEM).

22

# Raster versus Vector

<!-- Start of picture text -->
Raster Vector<br><!-- End of picture text -->

23

# Digital Elevation Models (DEM)

_https://www.esri.com/news/arcuser/0610/mosaicdataset.html_

24

# Spatial transformation

25

_Yudono (2017) https://iopscience.iop.org/article/10.1088/1755-1315/70/1/012002/meta_

26

# Introduction to ArcGIS Pro

- ➢ ArcGIS Pro is an advanced GIS application from Esri.

- ➢ Consists of maps, scenes , layouts , data , tables, and different tools that are structured in a project.

- ➢ ArcGIS Online is a cloud-based system built to encourage the sharing of GIS data and other resources between organizations and users.

- ➢ Both ArcGIS Pro and ArcGIS online required an account from ESRI that provides access to more data and tools.

- ➢ ArcGIS Pro can also run offline. ArcGIS Pro has the capability of ArcGIS desktop (ArcMap, ArcCatalog, and ArcToolbox). It also enables Python and ModelBuilder.

27

# ArcGIS Pro

28

# ArcGIS online - access

##### https://www.arcgis.com/index.html

29

30

31

# Homework and Resources

- ➢ Read Chapter 1 of course textbook: Overview

➢ Take the quiz to test your basic understanding (on BB)

### **Further resources**

ESRI training GIS Basics (components 1-3 only; 55 mins)

https://www.esri.com/training/catalog/5d9cd7de5edc347a71611cc - <u>c/gis basics/</u>

_Have a look at Geo-Wiki and OpenStreetMap_ https://www.geo-wiki.org/ https://www.openstreetmap.org/#map=6/54.910/-3.432

32
