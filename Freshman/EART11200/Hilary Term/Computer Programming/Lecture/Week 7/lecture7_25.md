---
title: "lecture7_25"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Lecture/Week 7/lecture7_25.pdf"
type: pdf
---

<!-- Start of picture text -->
pandas and [geospatial] data discovery<br><!-- End of picture text -->

#### practical 7

##### 'Vanilla' Python

Data types Loops Basic operations Conditionals **~~1 2~~**

# course layout

**~~3 4 5~~**

The Numpy Conway's Game Differential module Of Life Equations

Modules and Functions

##### Pandas and data discovery

Geospatial analysis

Statistical Cluster Analysis Analysis

**~~6 7 8 9~~**

<!-- Start of picture text -->
Creating a notebook assessment<br>select topic from weeks 4 - 9<br>10 11 12<br><!-- End of picture text -->

lecture + practical. Solutions are given

## recap

- Pandas allows us to store information in a dataframe

- Pandas can deal with various data types

- We can access entries in that dataframe according to certain criteria

- Dataframes have internal functions we can use to our advantage

What if we have data we want to perform statistical analysis on the data?

## geographic information systems (gis)

**Geographic** refers to the physical location or position on the Earth’s surface. **Information** refers to the data and details that can be used to represent and provide a better understanding of a speci�c location. **Systems** refer to a tool that makes many components work together to achieve a common goal. It helps us understand the data in a geographic context, which enables to make better-informed decisions in a variety of �elds such as urban planning, environmental management, and public health, among others that we will mention later.

" _...it is used by most industries. According to Data Bridge Market Research, Geographic information system market was valued at USD 9160.02 millionin 2021 and is expected to reach USD 22518.38 million by 2029.."_

## geographic information systems (gis)

We need a way to store, combine and integrate multiple types of geospatial data...

## vector and raster data

Some data �les are human readable. e.g. GeoJSON below

## in walks pandas....

"pandas...provides high-performance, easy-touse data structures and data analysis tools.."

## **in walks pandas....but, we need a geo extension...**

"pandas...provides high-performance, easy-touse data structures and data analysis tools.."

## workflow for todays practical - example of final figure produced in todays notebook

- Create data frames with geospatial data

- • Join polygon and point data

- • Clip using regional boundaries

- • Place all of this on a map

- • Visualise:

   - risk by authority

   - • distance between elements

## but the numbers in column geometry do not look like coordinates??

- A Coordinate Reference System (CRS) defines how the two-dimensional, projected map in your GeoDataFrame relates to real places on the earth.

- CRS can be represented in various formats, such as EPSG codes.

- • EPSG codes are short identifiers assigned to coordinate reference system (CRS) definitions. These codes are standardized and maintained by the EPSG (European Petroleum Survey Group) Geodetic Parameter Dataset.

<!-- Start of picture text -->
Correct CRS selection (via EPSG codes) is crucial for accurate distance and area measurements, especially<br>over large geographic extents. This is crucial when combining data from different sources to ensure they align<br>correctly.<br><!-- End of picture text -->

## but the numbers in column geometry do not look like coordinates??

As we combine data from different sources, we need to ensure they are based on the same CRS. Fortunately, GeoPandas allows us to move between different systems.

## plotting vector data on a map

## plotting vector and raster data on a map

## joining and clip data frames

Join is a GeoPandas function that joins two data frames using their spatial data. clip is a way of removing all data outside of a set of polygons we can use both to produce a map where a subset of data is presented

## distance functions

## workflow for todays practical - example of final figure produced in todays notebook

- Create data frames with geospatial data

- • Join polygon and point data

- • Clip using regional boundaries

- • Place all of this on a map

- • Visualise:

   - risk by authority

   - • distance between elements

## in walks GEopandas

"A GeoPandas DataFrame is two-dimensional sizemutable, potentially heterogeneous tabular data structure with labeled axes (rows and columns). A Data frame is a twodimensional data structure, i.e., data is aligned in a tabular fashion in rows and columns. "

<!-- Start of picture text -->
pandas and [geospatial] data discovery<br><!-- End of picture text -->

data data everywhere....in walks pandas and geo-pandas

<!-- Start of picture text -->
Lecture 7                                                  summary<br><!-- End of picture text -->

### interacting with geospatial data in python

- Data is everywhere.

- Geospatial data comes in vector and raster formats

- GeoPandas can load multiple �le types

- Some formats are humn reasdable, others are not

### geospatial plotting

- GeoPandas module allows us to plot both vector and raster data on the same map

<!-- Start of picture text -->
practical 7                                               goals<br><!-- End of picture text -->

### code

- Become familiar with GeoPandas

- Select a subset of data according to some criteria being met

- Plot vector and raster data

### general experience

- Start to develop skills to interact with geospatial data - GiS highly valuable

- Increase the diversity of problems you can solve
