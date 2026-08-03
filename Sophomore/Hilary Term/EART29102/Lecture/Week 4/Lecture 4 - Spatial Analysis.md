---
title: "Lecture 4 - Spatial Analysis"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 4/Lecture 4 - Spatial Analysis.pdf"
type: pdf
---

# Spatial Analysis

### Lecture content

- ➢ Concepts of spatial analysis and modelling.

- ➢ Spatial query using attributes and locations.

- ➢ Spatial operations.

- ➢ Spatial interpolation methods and errors.

## Spatial analysis definition and types

- ➢ A set of methods used to query features based on their attributes or analyse how layers interact spatially.

- ➢ Used to identify patterns, associations, and evidence of change through time and location.

- ➢ **Spatial query:** filtering and selecting data from a geodatabase based on attributes and location.

- ➢ **Spatial operations:** a type of spatial query class that includes operations such as intersection, containment, and distance calculations for objects in a given region or point.

- ➢ **Spatial interpolation:** estimates unknown values at specific locations based on known values from surrounding points.

## Spatial analysis and modelling

## Spatial query

##### ➢ Select, extract and interactive query.

##### ➢ Query by attribute.

- ➢ To retrieve all features with particular **attribute** values from one data layer or feature class in a spatial database and display their locations in a map.

##### ➢ Query by location.

- ➢ To find features from one or multiple data layers based on their **locations** relative to features from another layer in the same spatial database.

- ➢ To identify **attribute** values associated with features at particular locations.

## Query by attribute

➢ A query uses a specific database query language.

➢ Many GIS systems support SQL (Structured Query Language).

## Query by attribute and location

**Attribute** : ‘Retrieve all water mains installed before 2010 with a diameter less than 30cm’.

```
SELECT * FROM w_mains WHERE “year” < 2010 AND “diameter” < 30
```

The WHERE clause filters the results to only include those water mains that meet the two criteria.

**Location** : ‘Select all buildings that intersect with a given park’.

```
SELECT * FROM buildings WHERE ST_Intersects(buildings.geometry,
(SELECT geometry FROM parks WHERE name=‘Whitworth’))
```

The ST_Intersects function checks if the geometry of each building in the dataset intersects with the geometry of Whitworth Park.

There are large number of ST_geometry functions that can be used in a GIS.

### Example – query by attribute

### Geoprocessing operations (merge, reclassify and dissolve)

Assigning new values to raster dataset cells based on their pre-existing values is known as reclassification in GIS.

## Overlay analysis

➢ A process of stacking multiple data layers with a common georeferencing system on top of each other so that the relationships between features at each location can be analysed.

- ➢ The most common GIS operation for comparing and analysing multiple data layers simultaneously. E.g. calculating the number of properties within a flood risk zone.

- ➢ Overlay analysis can be conducted using either vector or raster data.

## Vector overlay - 1

➢ Two or more vector layers are combined to produce new geometries.

e.g. union

## Vector overlay - 2

➢ Two or more vector layers are combined to produce new geometries.

➢ _union_ Typical overlay operations include , _intersection_ , and _difference_ - named after the result of the combination of two layers.

## Raster overlay (map algebra)

➢ Raster overlay superimposes at least two input raster layers to produce an output layer. ➢ Each cell in the output layer is calculated from the corresponding cells in the input layers.

Map algebra

### Geometric and distance measurement

➢ Length, area, perimeter and shape. Useful for landscape metrics e.g. interaction between spatial pattern and ecological processes.

➢ Geometric properties and distances are usually not encoded during spatial data input. GIS offers measurement functions to calculate them.

## Measuring length, perimeter and area in raster

## Neighbourhoods: Buffers

Buffering is a distance measurement tool for vector data commonly available in GIS. It creates a zone around a feature or a set of features with a specific width.

## Neighbourhoods: Cost distance surface

➢ Cost-distance analysis measures how costly, or expensive, it is to travel over a surface.

➢ Simulates how a mover will experience the landscape as they travel through it. This is different from Euclidean distance, which captures how far a mover is from known locations in a straight line.

- ➢ Cost can be measured in topography, time, money, energy expended, or other forms.

## Neighbourhoods: Least cost path

➢ Calculates the lowest cost from a location to every other location and creates a distance surface in raster form. ➢ A least cost path represents the most efficient route through the landscape. e.g. wildlife corridors in fragmented habitat (foraging, range), pipeline or road planning, rescue operations, etc.

### Hedgehog movement patterns in urban landscapes

➢ Different hedgehog movement patterns depend upon the degree of predicted connectivity in urban landscapes.

➢ In highly connecting contexts (HCC), hedgehogs followed predicted low cost path (LCP) corridors, whereas in unconnected contexts (UCC) movements were random.

Balbi et al (2019) https://doi.org/10.1016/j.jenvman.2019.04.124

## Spatial interpolation

➢Estimating values of an environmental variable at locations whose values are unknown based on a sample of locations with known values. ➢Apply an interpolation method to a set of points with known values to create a continuous surface.

## Spatial interpolation methods

- ➢ Environmental data are often collected as discrete observations at points.

- ➢ Two common methods: Inverse Distance Weights (IDW) = deterministic and Kriging = geostatistical.

<!-- Start of picture text -->
IDW<br><!-- End of picture text -->

<!-- Start of picture text -->
Kriging<br><!-- End of picture text -->

## Inverse Distance Weights (IDW)

_zp is interpolated value, zi is known value at points; di = distance of points from z ; p = power term. p_

- ➢ IDW estimates a value of each location by taking the distance-weighted average of the values of sample points in its neighbourhood.

- ➢ Explicitly assumes that things closer to one another are more alike than those that further apart (Tobler’s first law of geography).

- ➢ As value _p_ increases, the weights for distant points decrease rapidly. If the _p_

- is very high, only the immediate surrounding points will influence the prediction.

## Spatial autocorrelation

#### -

###### **Random**

#### +

- ➢ Spatial autocorrelation is a statistical measure of Tobler’s first law of geography “Everything is related to everything else, but near things are more related than distant things”.

➢ **Positive** spatial autocorrelation is when similar values cluster together.

- ➢ **Negative** spatial autocorrelation is when dissimilar values cluster together

   - (i.e. nearby locations are more different than expected by chance).

- ➢ Spatial autocorrelation is an underlying assumption of spatial interpolation.

## Examples of IDW interpolation

_A power (p) of 1 smooths out the interpolated surface. Increases_ . _influence of more distant values_

_A power (p) of 2 increases the influence of close values._

## Kriging

- ➢ Kriging interpolates values and their probability at a specific location.

- ➢ Uses input data to build a mathematical function with a semivariogram, to create a prediction surface, and then validate the model with crossvalidation.

- ➢ A geostatistical method that provides an optimal prediction surface AND a measure of confidence in how likely that prediction will be true.

## Kriging – semivariance and distance

➢ Semivariogram(distance) = 0.5 * average((valuei – valuej)<sup>2</sup> )

- ➢ The formula involves calculating the difference squared between the values of the paired locations.

➢ The image shows the pairing of one point (the red point) with all other measured locations. This process continues for each measured point.

https://pro.arcgis.com/en/pro-app/latest/tool-reference/spatialanalyst/how-kriging-works.htm

## Semivariogram

➢ The semivariogram is a graph of the averaged semivariogram values on the y-axis and the distance (or lag) on the x-axis.

## Range, sill and nugget

The semivariogram defines the spatial structure that kriging uses to weight data points.

## Ordinary kriging

- ➢ The semivariogram defines the spatial structure that kriging uses to weight data points.

➢ **Ordinary kriging** uses a linear combination of the observed data values, with weights, to make predictions of values at unmeasured locations.

- ➢ **Simple kriging**

- ➢ **Universal kriging**

##### ➢ **Co-kriging**

## Kriging temperature variations

### Kriging error analysis

**Count** = number of known values. **Mean** = average difference between known and predicted values (should be close to zero).

**RMSE** = prediction accuracy (should be as small as possible). **RMSS** should be close to 1.

<!-- Start of picture text -->
Can use R 2  as estimate of model quality<br><!-- End of picture text -->

### Kriging examples - plastics

Coleby and Grist (2019) used a semivariograms and kriging to map the distribution of marine plastic pollution in Hong Kong.

_kriging variance_

https://doi.org/10.1016/j.ocecoaman.2018.12.021

### Kriging examples – crustal thickness

Kebede et al.(2024) used kriging to obtain a Bouguer anomaly map of the Main Ethiopian Rift (MER)

<!-- Start of picture text -->
https://doi.org/10.1016/j.ocecoaman.2018.12.021<br><!-- End of picture text -->

## Sources of error in interpolation

➢ Errors inherent in interpolation method measured in terms of root mean square error, RMSE or r<sup>2</sup>

➢ Sample data uncertainty too few sample points, limited or clustered distributions and uncertainty about locations and/or values. ➢ Edge effects distortions of the interpolated values near the boundary of the study area due to the lack of sample data outside the area. ➢ Outliers outliers can significantly affect the accuracy of kriging predictions.

## Homework and Resources

➢ Read Chapter 5 of course textbook: Spatial Analysis.

##### ➢ Take the quiz to test your basic understanding (on Canvas).

##### **Further resources**

ESRI training Getting started with spatial analysis (components 1-3 only; 1hr 15 min).

https://www.esri.com/training/catalog/5bca58f8f77b99238f8 45e1c/getting-started-with-spatial-analysis/

## OCR 补充（原文中无文字层的页面）

_(以下内容由图片 OCR 识别得到，原文件该处无可提取文字；识别可能有误，请对照原件。)_

### Page 7

Example — query by attribute

% Wet rissa
b st 4,574,268.86W 2.828,547.95N ftUS_¥
election: “jg Select By Attributes SB Switch

CANADA

Pe: ony
/ TR

Wan \
+ 2,730,163.67E 2,680,971.53N RUS ¥

Guif of

eee

Project Portal Favorite

BOB A

Select By Attributes
Input Rows:
| USA_Major_Cities
© The input has a selection. Records to be processed: 5
Selection Type

?

x

y|
~
ce

[ New selection
Expression
fa@ Load bal save X Remove

v so. OD

Where POPULATION + | is oreate ~ 10000

= r
[Ana + | |FEMALES ‘| is greate ~ | |MALES

+ Add Clause

C) Invert Where Clause

Project Portal Favorites

ABABA
Select By Attributes ? x
Input Rows
USA_Major_Cities ~| ae
© The input has a selection, Records to be processed: 3,305
Selection Type
[New selection =
Expression
lm@ load Fel Save Remove
v So. OD
Where [POPULATION | is greate * { 10000 +| *
‘And ~| [FEMALES + | [is greate ~ | MALES |x

+ Add Clause

(C Invert Where Clause

Select By Attributes ? x
Input Rows
USA_Major_Cities -l =
© The input has a selection. Records to be processed: 3,305 rs
Selection Type
New selection bd
Expression

la@ Load
v SaL@D

POPULATION > 10@@@ And FEMALES >» MALES

fal Save XX Remove

(_} Invert Where Clause

### Page 13

Map algebra

Type Operators/functions

Arithmetic +,-—, X, 4 square, square root, exponentials, logarithms
Logical AND, OR, NOT

Relational =>,25,5

Conditional IF...THEN..., IF...THEN...ELSE

Trigonometric (inverse) cosine, (inverse) sine, (inverse) tangent

Statistical maximum, minimum, mean, range, standard deviation, sum,

median, majority, minority, variety
