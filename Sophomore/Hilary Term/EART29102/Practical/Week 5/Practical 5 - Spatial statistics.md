---
title: "Practical 5 - Spatial statistics"
source: "Sophomore/Hilary Term/EART29102/Practical/Week 5/Practical 5 - Spatial statistics.pdf"
type: pdf
---

_EART29102 Practical 5_

# Practical 5: Spatial statistics

#### Learning outcomes

By the end of this practical you will be able to:

- Create standard deviational ellipses.

- Use the Average Nearest Neighbor tool.

- Use the Spatial Autocorrelation tool.

- Perform hot spot analysis

## Contents

|1|Introducton .................................................................................................................................... 2|
|---|---|
|1|.1<br>Descriptve statstcs ................................................................................................................ 2|
|1|.2<br>Inferental statstcs ................................................................................................................. 2|
|2|Load ozone data into Arc GIS pro .................................................................................................... 2|
|3|Locate directonal trends in the ozone data.................................................................................... 3|
|4|Run the Average Nearest Neighbor tool ......................................................................................... 4|
|5|Run the Spatal Autocorrelaton tool .............................................................................................. 5|
|6|Run the Hot Spot Analysis tool ....................................................................................................... 6|
|7|Create a density surface .................................................................................................................. 8|
|8|Challenge Exercise ........................................................................................................................... 9|
|9|Further resources .......................................................................................................................... 10|

This tutorial was originally developed by ESRI training Spatial Analysis with ArcGIS Pro

1

_EART29102 Practical 5_

## 1 Introduction

Spatial statistics are the application of tools and methods that use space and spatial relationships (such as distance, area, length, orientation, centrality, coincidence, connectivity, orientation) directly in their mathematical computations.

Spatial statistics allow you to do the following tasks:

- Minimize the subjectivity inherent in human visual interpretation of maps and spatial data.

- Identify and quantify patterns and trends in data that may not be revealed in visual analysis.

- Answer questions more confidently and make important decisions using more than simple visual analysis.

### 1.1 Descriptive statistics

Descriptive statistics return a summary about your data, whether the result is quantitative like a summary statistic (mean, sum, etc) or visual, such as a graph or feature class. In GIS, descriptive statistics commonly measure central tendency, dispersion or concentration, or orientation of spatial phenomenon.

### 1.2 Inferential statistics

In classical statistics, inferential statistics infer something about the entire population based on the distribution of values in a sample. A common example of inferential statistics is predicting the outcome of an election based on polls. Inferential statistic tests begin by identifying a null

hypothesis. The **null hypothesis** for pattern analysis tools is **complete spatial randomness** in either the **location** of features or the **values** associated with those features. Some spatial statistics tools return statistics that indicate the degree of statistical significance, which in turn provides you with a degree of confidence in rejecting or not rejecting the null hypothesis of complete spatial randomness.

Spatial statistics may seem daunting, but running the tools can quickly provide valuable information that you can use to understand your data and make informed decisions. Two common tools used are the **Directional Distribution** tool and the **Spatial Autocorrelation** tool.

- **Directional Distribution** tool: Creates standard deviational ellipses to summarize the spatial characteristics of geographic features, such as central tendency, dispersion, and directional trends.

- **Spatial Autocorrelation** tool: Measures spatial autocorrelation based on both feature locations and feature values simultaneously. Given a set of features and an associated attribute, it evaluates whether the pattern expressed is clustered, dispersed, or random.

In this exercise you will use various descriptive and inferential statistics tools to quantify patterns and relationships in atmospheric ozone sample data for California, USA.

## 2 Load ozone data into Arc GIS pro

The U.S. Environmental Protection Agency is responsible for monitoring atmospheric ozone concentration in California. Ozone concentration is measured at monitoring stations throughout the state. The concentration levels of ozone are reported for many stations.

Start ArcGIS Pro with a new projects (e.g. ozone).

**Add Data** from **ArcGIS online** by searching **California_Ozone_Map** and add the feature layer.

2

_EART29102 Practical 5_

The ozone dataset (O3_Sep06_3pm) was provided courtesy of the California Air Resources Board and represents the concentration of ozone measured on 6<sup>th</sup> September , 2007 between 3:00 and 4:00 pm in parts per million (ppm). The map displays the ozone concentrations across California. You can clearly see visual clusters of high and low ozone concentrations.

Open the **Attribute Table** of the O3_Sep06_3pm layer.

The table contains the name of 167 monitoring stations, their elevations, and the ozone measurements (in ppm). The layer is symbolized using the OZONE field.

Set the **Environments** so that analysis is restricted to the geographical boundary of California.

From the **Analysis** tab, click **Environments** .

Set the following environments:

**Extent: Same As Layer** – ca_outline then **Mask:** ca_outline

Click **OK**

**Save** the project.

## 3 Locate directional trends in the ozone data

In this step, you will use the **Directional Distribution** tool to identify trends in the ozone data.

Open the **Geoprocessing** pane (Analysis tab > Tools).

In the **Geoprocessing** pane, type **direction** .

**Open** the **Directional Distribution (Standard Deviational Ellipse)** tool, and set the following

parameters:

**Input Feature Class** : O3_Sep06_3pm

3

_EART29102 Practical 5_

**Output Feature Class** : Ellipses

**Ellipse Size** : 1 Standard Deviation

**Weight Field** : OZONE

Click **Run**

When the underlying spatial pattern of features is concentrated toward the centre with fewer features toward the periphery, one standard deviational ellipse polygon will cover approximately 63 percent of the features. The ellipse indicates a directional trend that is based on the orientation of the sample points.

Next, you will run the same tool using a different ellipse sizes to account for more sample points.

In the **Contents** pane, turn off the **Ellipses** layer.

In the **Geoprocessing** pane, modify the following parameters for the **Directional Distribution**

tool:

**Output Feature Class** : Ellipses2

**Ellipse Size:** 2 Standard Deviations

Click **Run** .

Choosing two standard deviations and including more of the sample points results in a larger

ellipse with a similar directional trend as the other ellipse for one standard deviation.

Turn **off** the **Ellipses2** layer.

## 4 Run the Average Nearest Neighbor tool

We will use the Average Nearest Neighbor tool to determine the degree of clustering or dispersion in feature locations.

In the **Contents** pane, open the **ca_outline** layer **Attribute Table** .

The **Average Nearest Neighbor** tool uses area as a parameter, so you will copy the area from the **ca_outline** .

In the table, note the **Shape_Area** value

In the **Geoprocessing** pane, click the **Back** button.

In the search field, type **average** .

Open the **Average Nearest Neighbor tool** , and set the following parameters:

**Input Feature Class** : O3_Sep06_3pm

Check the **Generate Report** box

**Area** : Type-in the **Shape_Area** value.

Click **Run**

The output from the Average Nearest Neighbor tool is a report, not a feature class.

4

_EART29102 Practical 5_

Hover the cursor over the **View Details** and open the **Report File (an html file)**

The null hypothesis states that the locations of the features are randomly distributed. However, the z-score (-3.30) returned from the Average Nearest Neighbor tool is statistically significant at a confidence level of 99 percent (i.e. p < 0.1), meaning that there is less than a 1 percent likelihood that the spatial pattern of ozone locations is the result of random chance. Look at the normal curve for a random distribution and note that the z-score is in the tail (blue zone) indicating the data are clustered.

**Close** the **Report** , and return to ArcGIS Pro.

## 5 Run the Spatial Autocorrelation tool

The Average Nearest Neighbor tool only looks at feature locations to determine if they are clustered or dispersed. If you want to determine if there is clustering in the attribute values (i.e. ozone concentrations) at those locations, you must run the Spatial Autocorrelation (Moran's I) tool.

In the **Geoprocessing** pane, go back to the search results and search for **spatial** .

**Open** the **Spatial Autocorrelation (Global Moran's I)** tool, and set the following parameters:

**Input Feature Class** : O3_Sep06_3pm

**Input Field:** OZONE

**Check** the **Generate Report** box

**Conceptualization Of Spatial Relationships** : Fixed Distance Band

**Standardization** : Row

5

_EART29102 Practical 5_

##### Click **Run** .

The warning is due to not providing a distance band or threshold distance. The software calculates a default value of 154,019 meters, or roughly 95 miles, to ensure that every feature has at least one neighbor. If you were investigating crime clusters, a distance of 800 meters might work because that is the average size of a city block. When choosing the appropriate distance threshold, it is often based on common sense, theory, and the field that you are working in.

Hover over **View Details** and **0pen** the **MoransI_Result** HTML file

The high z-score and low p-value indicates that you can reject the null hypothesis and conclude that the spatial distribution of high values and low values in the data is more spatially clustered than would be expected if the underlying spatial processes were random.

**Close** the report, and return to ArcGIS Pro.

## 6 Run the Hot Spot Analysis tool

In this step, you will perform hot spot analysis to determine where the clusters are located.

In the **Geoprocessing** pane, search for **hot** .

**Open** the **Hot Spot Analysis (Getis-Ord Gi*)** tool, and set the following parameters:

**Input Feature Class** : O3_Sep06_3pm

**Input Field** : OZONE

**Output Feature Class** : HotSpots

**Distance Band Or Threshold Distance** : 150000

6

_EART29102 Practical 5_

150000 is the value that the Spatial Autocorrelation tool used as the threshold distance.

Accept all remaining default settings and click **Run** .

In the **Contents** pane, turn off the O3_Sep06_3pm layer.

Statistically significant hot spots of high ozone values are in north-central California. These hot spots indicate higher ozone values surrounded by other higher ozone values.

Zoom into the central area:

Click a few of the red points.

The OZONE values are all close to one another and are relatively high, around 0.08 to +1.0. Another benefit of performing hot spot analysis is seeing where there are clusters of low values, or cold spots.

Zoom to the southern part of California where there are cold spots (blue points).

7

_EART29102 Practical 5_

Click on some points.

Most of the ozone values for the cold spots are around 0.05 or lower.

In the **Contents** pane, right-click **HotSpots** and choose **Attribute Table** .

Each point is assigned a value for z-score and p-value, and those values are added to the attribute table. When you have a combination of a high z-score and a low p-value, it indicates spatial clustering of high values. The lower or negative z-scores in combination with a lower p-value indicate spatial clustering of low values.

**Close** the **Attribute Table.**

## 7 Create a density surface

In this step, you will compare the results of hot spot analysis with a density surface, or heat map.

In the **Contents** pane, turn off the **HotSpots** layers.

In the **Geoprocessing** pane, search for **kernel** .

**Open** the **Kernel Density** tool, and then at the top of the pane, click the **Environments** tab.

Set the **Cell Size** to **Maximum Of Inputs** .

At the top of the pane, click **Parameters** , and then set the following parameters:

**Input Point Or Polyline Features** : O3_Sep06_3pm

**Population Field** : NONE

**Output Raster** : Density

Accept all remaining default settings and click **Run**

The density surface aligns well with the sample points, as it should, because you did not use a population field and only used the point location to create the surface. However, the symbology of the heat map makes it difficult to interpret patterns.

8

_EART29102 Practical 5_

In the **Contents** pane, turn on the **HotSpots** layer and turn off the **O3_Sep06_3pm** layer.

In the map, zoom in on the northernmost part of California, where there is a high density of sample points.

The hot spots at a 99% confidence interval are not all located in the high-density area of the points. The density surface is symbolized based on density of features, not ozone values. Comparing a density surface to a statistical result demonstrates how spatial statistics quantify spatial patterns and how heat maps do not.

Now repeat with **Population Field** : OZONE

This will give a kernel density surface map showing ozone concentration densities (in ppm/km2) compare it with your sample point density map.

**Save** the project.

## 8 Challenge Exercise

Use the methods of spatial interpolation that you learned in last week’s practical (IDW and krigging) to produce continuous surfaces of ozone concentration from the monitoring locations.

To limit your analysis to the boundary of California then Clip:

9

_EART29102 Practical 5_

For IDW remember to optimise your power and make a note of the mean and RMSE

Remember that krigging assumes data is normally distributed. Check this by making a histogram of ozone values – are they normally distributed? If not then which type of transformation works best to make them normal?

If your data need to be transformed then remember to do this as an option for krigging but you may need to change the model. I tried both “none” with “stable” model, and a “log” transform and “exponential” model as best fit for the semivariogram. Results were similar.

Remember to make a surface of standard errors as part of your krigging analysis.

## 9 Further resources

This video is quite good at explaining the concepts with everyday examples (it is quite long though, 1 hr).

<u>Spatal Data Mining I: Essentals of Cluster Analysis</u>

10
