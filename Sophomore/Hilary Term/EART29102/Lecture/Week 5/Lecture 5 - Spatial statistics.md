---
title: "Lecture 5 - Spatial statistics"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 5/Lecture 5 - Spatial statistics.pdf"
type: pdf
---

# Lecture 5: Spatial statistics

- ➢ Spatial sampling design.

- ➢ Central tendency, dispersion and direction.

➢ Inferential statistics and spatial randomness.

- ➢ Spatial autocorrelation.

- ➢ Spatial clusters analysis.

➢ Nearest Neighbour, Moran's I statistic (Cluster/Outlier), Getis-Ord (Hot Spot) and Kernel density estimation methods.

# Spatial statistical analysis

###### Applying spatial statistical methods and tools to spatial data.

➢ Minimise the subjectivity inherent in human visual interpretation of maps and spatial data.

➢ Identify and quantify patterns and trends in data that may not be revealed in visual analysis. ➢ Answer questions more confidently and make important decisions using more than simple visual analysis.

Hotspot analysis results for mercury, lead, copper, zinc, nickel, and fluoranthene within the central Appalachia region (Neville et al. (2022)DOI: 10.1080/02626667.2022.2052073

# Spatial sampling methods

_Random Stratified_

_<u>Systematic Clustered</u>_

_<u>Transect</u>_

# Descriptive statistics

- ➢ Descriptive statistics summarise data (quantitative, visual).

- ➢ Commonly measure central tendency, dispersion or concentration, and orientation of spatial phenomenon.

###### ➢ Central tendency

- ➢ _describe the centre of a spatial distribution._

###### ➢ Dispersion

- ➢ _describe the degree of dispersion of geographical features around the centre of their spatial distribution._

###### ➢ Direction

- ➢ _describe directional spread of data (e.g. wind directions, animal migrations, pollution pathways, volcanic plumes, etc)._

## Measures of central tendency and dispersion

# Directional distribution

_>100 acre wildfire burns 1970-2020_

_https://link.springer.com/article/10.1007/s13753-022-00396-4_

# Inferential statistics

➢ Inferential statistics means to infer something about the entire population based on the distribution of values in a sample.

- ➢ Statistical significance is the probability that the observed spatial pattern is not likely due to chance alone (random).

➢ _The observed spatial pattern is considered significant if it has been predicted as unlikely to have occurred by chance._

- ➢ Significance or hypothesis testing.

➢ _Determine whether the spatial pattern quantified by a statistical measure could have arisen by chance alone or through sampling error._

# Complete spatial randomness

# Null and alternative hypotheses

#### ➢ Null hypothesis (H0).

➢ **_always_** _stated as being no spatial pattern, or no relationship between two observed spatial patterns._

- ➢ Alternative hypothesis (Ha).

   - ➢ _opposite to the null hypothesis._

- ➢ Significance test – accept or reject the null hypothesis.

_Standard normal distribution for randomness_

# _z-_ scores and p-values

➢ z-score represents a deviation from the mean in a distribution.

- ➢ A p-value (confidence level) dictates the critical z-score for rejecting or not rejecting the null hypothesis (H0).

<!-- Start of picture text -->
  = 0.05 means a<br>probability of rejecting H0<br>with 95% confidence.<br>z-values<br><!-- End of picture text -->

 _= 0.05 means a probability of rejecting H0 with 95% confidence. z-values_

## Finding _p_ -values in the probability distribution of the _z_ scores

The exact probability of getting a value of the test statistic of a given magnitude if the null hypothesis is true is called the _p-value_

## Nearest neighbour analysis (NNA)

- Measure the distance of each feature to its nearest neighbour (r0) and compare the observed distances with that expected from a random spatial pattern (re).

- Uses only feature location and **does not** consider the feature values at all.

- Ratio (R) = mean observed/ mean random distances.

R < 1 then tendency toward clustering

R = 1 then tendency to be random

R > 1 tendency to be dispersed.

_Q. Are these sample locations random located from eachother?_

# Nearest neighbour analysis

# NNA examples

###### Mineral textures

Tree surveys

###### Paleoecology

###### Earthquakes

# Spatial Autocorrelation

- ➢ Distance methods using both feature locations and feature values simultaneously.

- ➢ Evaluates the spatial autocorrelation.

- ➢ Determines if pattern is clustered, dispersed, or random.

<!-- Start of picture text -->
negative random positive<br><!-- End of picture text -->

# Global Moran’s _I_

Detects spatial clusters of features with high or low values (and spatial outliers). _Works with attribute values._

<!-- Start of picture text -->
Q. Do similar values<br>cluster together across<br>the whole study area?<br><!-- End of picture text -->

# Local Moran’s _I_

###### ➢ Local Moran’s I shows where clusters occur and identifies local outliers.

_Mashhoodi (2024) https://doi.org/10.1007/s12061-023-09555-6_

# Hot spot analysis (Getis-Ord Gi*)

<!-- Start of picture text -->
Q. Where are the unusually high<br>or unusually low values located?<br><!-- End of picture text -->

Q. Where are the unusually high or unusually low values located?

The hot spots (red) indicate statistically significant clustering of higher values. Cold spots (blue) are clusters with low values. _Works with attribute values._

# Kernel density estimation (KDE)

➢ Transformation from point objects to a density surface to visualize a point pattern to detect hot spots where the local density is estimated to be high.

- ➢ Density at any location in the study area.

➢ estimated by counting the number of objects (or events) in a region (=kernel) centred at the location p where the estimate is made

   - ➢ simple kernel: circle centred at the location p.

   - ➢ more sophisticated: a kernel function weighting nearby events.

- ➢ Density is scale dependent.

# Kernel density surface

➢ Kernel function (e.g., bell shape) for the local density.

- ➢ Each point is replaced by a kernel.

- ➢ Density surface is the sum of these.

- ➢ Density surface estimates the variation of the density of discrete events (events = point objects).

### Heat map using kernel density: sample point

<!-- Start of picture text -->
Sample Points<br>(number/km 2 )<br><!-- End of picture text -->

## Heat map using kernel density: ozone

<!-- Start of picture text -->
Ozone (ppm/km 2 )<br><!-- End of picture text -->

# Kernel radius (bandwidth)

1500 km

15km

optimised 99.3 km

Smoother (global average) Isolated on individual values

# Homework and Resources

➢ Read Chapter 6 of course textbook: Spatial Data Exploration with Statistics (you do not need to learn any statistical formulae).

- ➢ Take the quiz to test your basic understanding (on Canvas).

##### **Further resources**

ESRI training: Mapping Clusters: Introduction to Statistical Cluster Analysis (50 mins).

https://www.esri.com/training/catalog/5d39b6106b9c176 64bb656eb/mapping-clusters-introduction-to-statisticalcluster-analysis/

24
