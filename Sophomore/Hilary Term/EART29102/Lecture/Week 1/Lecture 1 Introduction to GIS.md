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

## OCR 补充（原文中无文字层的页面）

_(以下内容由图片 OCR 识别得到，原文件该处无可提取文字；识别可能有误，请对照原件。)_

### Page 9

Non-spatial data: a summary of the Spatial data:
locations of the landslides occurred in Australia since 1900

[DATE | Oo: | ae anes) |. oe N

23/03/1997| Trinity Beach, Cairns ldebrisfall | _145.70|
ees basset sn foteane [oreo | ve
debris flow 1/04/1911|Nisbet Range, 5 km E of Cairns debris flow 145.80]
debris slide 1/01/1925}
Pest saul arn | — ar
debris topple 30/04/1988]|Coledale debris flow 150.93}
dry sand flow 22/09/1983|Sulphur Creek, NWTasmania___—[debrisflow | 146.02|
learth block slide 1/05/1996] Mt Mitchell, near Cunningham's Gap, Qld [debris flow | 152.40]
learth fall 19/01/1997}

earth flow
earth slump
rock fall
rock slide
rock slump

rock topple
slump-earth flow
slump and topple
soil creep
wet sand or silt flow

debris flow 148.31,
debris flow 146.78)
debris flow 146.84

30/07/1997|Thredbo, Snowy Mountains

10/01/1998|Mt. Stuart, Townsville, Queensland

11/01/1998|Near Kelly St, Nelly Bay, Qld Y
7/08/1998| Below Seaforth Crescent,Sydney ebesflon |_sa2a

17/08/1998] Wollongong debris flow

11/02/1999] Kuranda Range Road, Kuranda, Qid

11/02/1999

3/03/1999|Great Western Tiers, Meander, Tasmania_|debris flow 146.62!
debris flow 150.83,

23/10/1999] Nareena Hills, Wollongong

bh 7
2 en hs %
Darwin ah (
ne S , “4
| " e } a
we )
% Townsville
pa Northern Territory ic
p Alice Springs,
ee

\ Western Australia |

\ °.

) South Australia
\ ‘~ | }

\ oe Dd
Perth)” a FS, 5 . New South Wales? RJ e

, aren LS fadetaide oo . tial
EPe | Ney
L = Viototia 93 NS

Ca '° >

Melbourne
0

© Landslide ocurrence
0 150 300 600 Kilometers.
Ses es eres

. }
>) a
Tasmania X sed Hobart

### Page 25

Spatial transformation

### Page 28

ArcGlS Pro

Untitled | 2 Command Search (ait+Q) | ray.burgess@manchester.ac.uk_UoManchester - The University of Manchester RB) =? = o x
View Edit Imagery ~— Share
Cd | BI a
cut (BB Add Graphics Layer yu Attributes & fin Ai Pause 2 Lock El ‘Syne
cov | ilseze a ¢| oF | = 18 arnoees 2, | lc .
Paste tpladinted * Bookmarks Go | Basemap Add Select Select By Select By Measure Locate Infographics Coordinate Convert Download *
. Copy Path | . ToXY Data Attributes Location «!! Zoom To . Conversion  @@ More ~ . Map~
ics | iis ae es 4 ay a eee -
Contents, vax ~ Catalog vax
h Pp ~| Project Portal Favorites =
T
LGU/ROR ©[a[senroes
eee ;
Drawing Order > gy Teo
4(E] Map » (Databases
[World Topographic Map > Styles
(J World Hillshade » ie rote
> GH Locators
Rox
ie
ruRore
arnica
souTn
Samenica
ANTARCTICA
109.4632905°E 80.5947417°N v selected Features 0| |i Catal... |Geop.. Modi. Creat... Elem... Symb..

28

### Page 30

- = z _? Fy) A Ray Burgess
Home Gallery Map Scene Groups Content Organization al Anise

ray.bt

‘'t ANC HESIE R

Theiprersty of Manchester,

aN

ArcGIS Online Spatial Data Infrastructure

Explore, Create and Publish Spatial Data for Teaching and Research @ The University of Manchester

Web Mapping Application Web Mapping Application Web Map Web Map
A socio-economic analysis of th... Access to Alexandra Park, Man... Looper Project Population Den... Peak District National Park Wild...

### Page 31

. .
@esri Products Industries Support & Services Stories About Q & Q

A | Esri Academy

Catalog Certification My Academy

Courses for ArcGIS Online

ArcGIS Online training options accommodate different schedules, learning styles, and experience levels.

Whether you have an ArcGIS Online public account or you're a member of an ArcGIS Online Organization with a
curated collection of mapping capabilities and content at your fingertips, the right course can help you be more
productive, faster.

Getting Started

Gain the skills you need to author and share informative web maps, explore data, and perform analysis.

R-LEL EB COURSE

Creating Stories with ArcGIS ArcGIS Online: Essential Workflows ArcGIS Online Basics

2 Days (16 Hours) 1 Day (8 Hours) 1 Hour, 50 Minutes

Free

ee60e 9 ®@ eeee¢ 9 © e86ee¢ 9 ®@

31
