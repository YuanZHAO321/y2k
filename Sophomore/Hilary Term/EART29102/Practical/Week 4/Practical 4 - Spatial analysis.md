---
title: "Practical 4 - Spatial analysis"
source: "Sophomore/Hilary Term/EART29102/Practical/Week 4/Practical 4 - Spatial analysis.pdf"
type: pdf
---

_EART29102: Practical 4_

# Practical 4: Geospatial analysis

#### Learning outcomes

By the end of this practical you will be able to:

- create a continuous temperature map of Africa and the Middle East from a dataset of sample points.

- analyse the distribution of the sample data with histograms.

- create interpolated surfaces using the inverse distance weighting and kriging methods.

- compare the accuracy of different surfaces using cross-validation.

- map the standard error of prediction for a chosen surface.

## Contents

|1|Introducton .................................................................................................................................... 2|
|---|---|
|2|Create histograms of data distributon ........................................................................................... 2|
|3|Geostatstcal Analyst ...................................................................................................................... 5|
|4|Interpolate an average annual rainfall surface using Inverse Distance Weightng (IDW) ............... 5|
|4|.1<br>Use a projected coordinate system ......................................................................................... 5|
|4|.2<br>Geostatstcal Wizard to apply IDW ......................................................................................... 6|
|4|.3<br>Optmising the IDW ................................................................................................................. 9|
|4|.4<br>Comparing cross-validaton statstcs for the IDW analyses.................................................. 10|
|5|Create geostatstcal surfaces using kriging................................................................................... 11|
|5|.1<br>Measured versus predicted correlaton coefcient .............................................................. 13|
|6|Map the standard error estmates ................................................................................................ 14|
|7|Challenge Exercise ......................................................................................................................... 16|
|8|Further resources .......................................................................................................................... 16|

This tutorial was originally developed by Esri's Learn Team.

You can find the official maintained version at this location

<u>htps://learn.arcgis.com/en/projects/interpolate-temperatures-using-the-geostatstcal-wizard/.</u>

You can find other tutorials in the tutorial gallery [htps://learn.arcgis.com/en/gallery/].

1

_EART29102: Practical 4_

## 1 Introduction

Many natural phenomena occur continuously across a landscape, for example, the distribution of nutrients in soil, dissolved oxygen in seawater, or rainfall. It is unrealistic to take measurements of these phenomena everywhere; you can only collect measurements at a set of sample locations. Using geostatistics, these sample measurements can be used to predict values at other, unmonitored locations. Many geostatistical methods also allow you to measure the uncertainty of your predictions.

Geostatistics is used widely for mapping natural phenomena in many fields, including meteorology, oceanography, geology, forestry, and the soil sciences. It is also applied to unnatural phenomena such as pollution. You have likely seen and used many maps that were created with the help of geostatistics.

The first step before undertaking any geospatial interpolation is to visualize the data and check that it is not highly skewed, has any extreme outliers and generally follows a normal distribution. We will do this first before applying spatial interpolation methods.

## 2 Create histograms of data distribution

First, you'll download the project package and use the data stored in this package throughout the tutorial to interpolate temperatures through the Geostatistical Wizard.

Download the **InterpolateTemperatures** project package from ArcGIS online.

The map shows temperature point data across Africa and the Middle East

The points on the map represent temperature samples. Each point stores average temperature values for each month. You will examine the data distribution of some of these fields to determine which to use for interpolation.

Spatial interpolation works best when the data points are fairly evenly distributed, are densely populated; and the amount of variation look similar across the area.

In the **Contents pane** , right-click the **Temperature** layer. Select **Create Chart** and choose **Histogram** .

2

_EART29102: Practical 4_

Both the Chart Properties pane and an empty chart view appear.

In the **Chart Properties** pane, change **Number** to **Jan Avg. Temp C** (short for January Average Temperature in Celsius) and check the box for **Show Normal distribution** .

The chart view updates to show a histogram representing the maximum temperature values from the point data. You can see that the values range from -10.2 to 30.1°C. The values shown on the axis may vary, depending on the width of the pane.

3

_EART29102: Practical 4_

The curved black line represents the normal distribution of the chart. Data with a normal distribution has a bell-shaped curve. You can see that the distribution of average temperatures in January is not normal, but rather it is skewed to the right.

In the **Chart Properties** pane, change **Number** to **Aug Avg. Temp C** . The histogram updates to the new field.

Temperatures in August have more of a normal distribution. Interpolation methods are most effective when the data is close to a normal (bell-shaped) distribution, and some geostatistical methods require that the data be normally distributed.

Check the histogram for any outliers and note the amount of skew and kurtosis.

**Kurtosis** is a measure of how sharp or flat the peak is in a distribution. A value of zero is a normal distribution, a negative value is flatter than normal and a positive value is more peaked than normal.

**Skew** is a measure of the symmetry of the distribution: a value of zero means a symmetric distribution; a positive value means the distribution is asymmetric and skewed to more positive values; and a negative value means asymmetry towards the negative side of the distribution.

_For both kurtosis and skew a value between -1 and +1 is usually taken to be a normal distribution._

An alternative way to check whether your data is normally distributed is with a Normal QQ Plot (an option in the **Create Charts** menu). A Normal QQ Plot compares how your data lines up with normally distributed data. If all points have a perfectly normal distribution, all your points would fall on the 45° line. In our case, the data follows a straight line. Try this for yourself.

Close the chart view.

On the **Contents pane** , right-click the **Temperature** layer and choose **Symbology** .

The Symbology pane appears.

Change **Field** to **Aug Avg. Temp C** .

4

_EART29102: Practical 4_

The map updates to show temperatures for August.

## 3 Geostatistical Analyst

The Geostatistical Wizard in ArcGIS Pro offers many different interpolation methods for creating predicted surfaces. Usually, you will not know which one to use until you have tried several and compared their results.

Check the ArcGIS Pro **Geostatistical Analyst** extension is available.

**Project** > **Licensing** > **Esri Extensions** the **Geostatistical Analyst** box is checked.

If not checked, then add it by clicking **Configure your license options** and selecting Geostatistical Analyst from the list. The **Geostatistical Analyst** toolbar is added.

## 4 Interpolate an average annual rainfall surface using Inverse Distance Weighting (IDW)

The first method we are going to try is Inverse distance weighting. IDW is a mathematical (deterministic, i.e. non-geostatistical) method that assumes closer values are more related than further values with its function. It is one of the simpler methods to apply.

### 4.1 Use a projected coordinate system

In the **Contents pane** , right-click the **Temperature** layer and choose **Properties** .

##### The **Layers Properties** : **Temperature** pane appears.

Click the **Source** tab.

Scroll down and click **Spatial Reference** to expand that section.

The table's first parameter is **Projected Coordinate System** .

5

_EART29102: Practical 4_

Geostatistics relies on distance measurements. To minimize the distortion of these distances, your input data must use a projected (rather than geographic) coordinate system. You can assign one using the Project geoprocessing tool.

These data uses an Equidistant Conic projection centered on Africa. There is no projection that can perfectly preserve all distances on your map, but equidistant projections will do a better job of this than others. The choice of projection is more important when mapping a large area, such as a continent.

Click **Cancel** to close the **Layer Properties** window.

- 4.2 Geostatistical Wizard to apply IDW

On the ribbon, on the **Analysis** tab, in the Workflows group, click **Geostatistical Wizard** .

Under **Deterministic methods** , choose **Inverse Distance Weighting** . (You may need to scroll down to find this option.)

For **Data Field** , choose **Aug Avg. Temp C** .

6

_EART29102: Practical 4_

Click **Next.**

On this page you can interactively change the parameters of the IDW method and see how the model responds in the preview map. The **Identify Resu** lt section tells you the predicted value for any location.

In the **Geostatistical Wizard** , click some different parts of the preview map to see the predicted temperature for that area in the **Identify Result** section.

Under **General Properties** , change **Neighborhood Type** to **Smooth** . The smooth option will generally make the prediction surface smoother and less jagged.

The preview map updates. When **Neighborhood Type** is **Standard** , there is only one circle on the preview map. When it is **Smooth** , there are three concentric circles.

The circles on the preview map represent the search neighborhood. To predict a new value, only the sample points that are nearby—within the search neighborhood—are considered.

7

_EART29102: Practical 4_

Verify that **Smoothing Factor** is set to 0.2.

Click **Finish** .

##### On the **Method Report** , click **OK.**

A new layer is added to the map, representing a surface of maximum temperature for the Africa region.

In the **Contents** pane, select Inverse Distance Weighting select **properties** and rename the layer **IDW Smooth** .

Now we will use the **Oceans** layer as a **Mask** to restrict the temperature interpolation to the continental areas.

Select **Geostatistical Layer** and **Masking** and tick the box labelled **oceans** .

8

_EART29102: Practical 4_

Note you may need to click the layer off then on again to see the masking.

The map now shows temperature predictions for places that had no temperature data.

##### 4.3 Optimising the IDW

Next, you will create a slightly different surface using the same data and the same method.

On the ribbon, on the **Analysis** tab, click Geostatistical Wizard.

Confirm that the selected method is **Inverse Distance Weighting** and the selected **Data Fiel** d is **Aug Avg. Temp C** . Click **Next** .

For **Neighborhood Type** , choose **Smooth** .

Click the **Optimize** button in the **Power** parameter.

The Power value changes to 3.1076.

Not all the points in the search neighborhood are considered equal. Those that are nearer to the location being predicted are given more weight in the calculation.

If Power is 0, all points in the neighborhood are weighted equally. The higher the power, the more rapidly the weights decrease with distance. A higher power of 3.1 results in a surface that appears more localized and less general, since points that are farther away have less of an influence.

##### Expand **Weights** and scroll through the list to find weights of different colours.

This list represents all of the points within your search radius and includes the weights assigned to them.

Click some of the values in the list to see the points selected on the preview map. Red points will exert more influence over the prediction than green ones.

##### Collapse **Weights** and click **Next** .

The Cross validation window provides information about how reliable your interpolation will be.

9

_EART29102: Practical 4_

The information on this page allows you to assess the accuracy of the prediction surface. It does this by removing a single point from the dataset and using all remaining points to predict the value of the removed point.

The scatter plot compares predicted values (on the x-axis) to measured values (on the y-axis) and is considered best when the thin gray line coincides with the thick blue line.

The **Mean** value tells you if the model is skewed toward predicting values that are too high or too low. It is best when it is closest to 0.

The **Root-Mean-Square** value is almost 2.5. This indicates that on average, the predicted temperature values differed from the measured values by about 2.5° Celsius.

On the **Method Report** window, click **OK** .

A new layer is added to the map.

**Mask** with the **oceans** layer.

Rename the layer **IDW Smooth Optimized** .

In the **Contents pane** , turn off the **Temperature** point layer.

**Uncheck** and **check IDW Smooth Optimized** to compare it with **IDW Smooth** noting any differences.

- 4.4 Comparing cross-validation statistics for the IDW analyses

In the **Contents pane** , select both **IDW Smooth** and **IDW Smooth Optimized** .

Note: To select more than one layer, press the Shift key while selecting layers.

10

_EART29102: Practical 4_

Right-click and choose **Cross Validation** .

Two Cross validation window for each layer appears. One of them is blocking the other from view.

Move the window aside so you can see both at once.

These are the same Cross validation windows that were shown in the Geostatistical Wizard. You already reviewed one of them, but the results are sometimes more useful when you can compare them between multiple prediction surfaces.

The Summary tab reports numerical errors for each surface. The closer the Root-Mean-Square value is to 0, the more accurate the created surface is.

IDW Smooth Optimized has a Root-Mean-Square value of 2.4998 and IDW Smooth has a value of 2.669.

IDW Smooth Optimized has the smaller error value and so can be considered the more reliable prediction surface.

**Close** both **Cross validation** windows.

In the **Contents pane** , select only **IDW Smooth** . Right-click this layer and choose **Remove** .

Click the **Save** button on the Quick Access Toolbar

Inverse distance weighting is considered an easy and fast interpolation method. It is good for getting an initial picture of the phenomenon you are mapping, and sometimes you may need to use it because it will follow measured values exactly. But it can also produce a ring effect around islands in your data.

## 5 Create geostatistical surfaces using kriging

Next, you'll try kriging to see if you can get more accurate results. Kriging is a very flexible geostatistical method. This means that you can adapt it in many ways to suit your data, but it also means that there are many more choices that must be made.

Open the **Geostatistical Wizard** .

Under **Geostatistical methods** , choose **Kriging / CoKriging** and click **Next** .

Under **Ordinary Kriging** , choose **Prediction** to create a surface of predicted values similar to the ones you created earlier using IDW.

For now, you will create a surface with the default parameters for ordinary kriging.

Click **Finish** and click **OK** .

11

_EART29102: Practical 4_

A new layer is added to the map.

Rename the layer **Kriging Default** .

Compare Kriging Default to IDW Smooth Optimized. The new layer is much more general in its pattern. Next, you’ll change some of the parameters to try to create a better geostatistical surface.

Open the **Geostatistical Wizard** .

Confirm that the selected method is **Kriging/CoKriging** and click **Next** .

Under **Ordinary Kriging** , select **Prediction** and click **Next** .

On the **Semivariogram/Covariance Modeling** page, change **Function Type** to **Semivariogram** and click the **Optimize model** button.

The Optimize button finds the parameters that result in the smallest prediction errors. Notice that the semivariogram map and some of the parameters have changed. In this case, the change is minimal.

Click **Next.**

On the **Searching Neighborhood** page, change **Sector Type** to **8 Sectors** .

Increasing the number of sectors ensures that neighbors are searched for in all directions, and a large cluster of nearby points in only one direction will not have all of the influence over the predicted value.

Click **Next** and review the results on the **Cross validation** window.

12

_EART29102: Practical 4_

Note that kriging provides you with many more values than inverse distance weighting.

Click **Finish** and click **OK** .

Another layer is added to the map.

Rename the layer **Kriging Modified** .

Compare Kriging Modified to Kriging Default. They are very similar.

In the **Contents pane** , select **Kriging Default** and **Kriging Modified** . Right-click and choose **Cross Validation** .

Arrange the windows so you can see both at once. Analyze the values on the Summary tab.

Compare the statistics. Numbers closer to zero indicate better accuracy. The exception is RootMean-Square Standardized. In this case, values closer to 1 are desired.

It is not immediately obvious from these values which surface is better. Kriging Default has better values for every category except Root-Mean-Square. However, this does not necessarily mean it is better.

If any of these values are too far off, you should eliminate that layer. But in this scenario, both layers show good cross-validation results, so you can use Root-Mean-Square as the tie breaker value. It is also desirable that the Root-Mean-Square and Average Standard Error values be close to one another. If there is a large difference between these values, it may indicate that the prediction is unstable.

### 5.1 Measured versus predicted correlation coefficient

There is one further parameter we can use which is the goodness of fit (R-squared) between measured and predicted values. To do this we need to run the cross-validation tool from the geoprocessing tool and extract points into a new feature class.

From the **Analysis** on the ribbon, select **Tools** and search for **Cross validation**

Select **Kriging default** as the **Input geostatistical layer**

**Output point class feature** as **Kriging default points** .

Click **Run**

13

_EART29102: Practical 4_

A new layer is added to the map

Repeat this procedure for the **Krigging modified** geostatistical layer

Make scatter plots of measured **Aug Avg. Temp C** (x) versus **Predicted** (y) and note the R^2 values.

Kriging is a more advanced method than IDW and requires you to make more decisions. But this allows you to experiment with the parameters until you find those that are a good fit for your data and phenomenon. Kriging also gives you more tools to assess the accuracy of your results, such as a map of the standard error estimates, which you will create next.

## 6 Map the standard error estimates

You have now made four different surfaces of temperature covering Africa and the Middle East. Each was interpolated from the same data, but each showed a different surface. Clearly these predictions are useful, but they cannot be taken as fact. Some parts of the surface (where there are many data points) can be considered more accurate and reliable than others (where the data is scarce). It is useful to map these degrees of uncertainty to aid decision makers.

##### In the **Contents pane** , select **Kriging Modified** .

On the ribbon, on the **Geostatistical Layer** tab, change Display Type to **Standard Error** .

The map changes to become mostly red.

In the **Contents pane** , turn on **Temperature** .

14

_EART29102: Practical 4_

Standard errors are measures of uncertainty for the predicted values. The dark-red areas on the map have larger standard error values and therefore lower certainty in the predicted values. Lighter areas are those where you can place more trust in the results. This map suggests that the results have the greatest standard error in the ocean. This makes sense, because there were no sample measurement points in the ocean (although there were some on small islands).

For the **Kriging Modified** layer, change the **Display Type** back to **Prediction** .

**Save** the project.

Geostatistics can help you map many phenomena as continuous surfaces even though you only have discrete point data. This can be very useful for visualizing patterns and performing analysis. You may not have a weather station in your study area, but a set of weather stations in a wider region can provide the data you need to understand and predict temperatures everywhere.

15

_EART29102: Practical 4_

The Geostatistical Wizard offers many interpolation methods, and each one has parameters that can be tweaked to produce different results. Why? Depending on the phenomenon you are mapping, and the data you have available, one model may give you more reliable results than another. If you are going to make decisions based on an interpolated surface, finding the most accurate model is critical.

You can compare the cross-validation results to determine which method is working best for your data. Once a surface has been created, some parts of it will offer more accurate predictions than others. You can visualize the surface by its standard prediction error to understand where the prediction is most reliable.

## 7 Challenge Exercise

The four maps you made were all derived from the same input data, but they looked different from one another. Now that you know how maps with interpolated surfaces are made, do you trust them more or less? Geostatistical models can be tweaked to create more accurate results. On the other hand, the map maker might have an agenda that they want to promote, and they may tweak the geostatistical parameters to emphasize a trend.

This project contains five more maps—one for each of the other continents. You can find them in the Catalog pane, on the Project tab, in the Maps folder.

Work through this practical exercise again using one of these maps. For Africa and the Middle East, you found that Aug Avg. Temp C was the best field, and Kriging Modified was the best surface. For another continent, you may find that different parameters yield better results.

## 8 Further resources

ESRI training course for Geostatistical Interpolation.

<u>htps://www.esri.com/training/catalog/5d8a8c9055cf937306dba777/geostatstcal-interpolatonintroducton/</u>

Co-Kriging Interpolation of annual average temperature – ArcGIS storybook

<u>htps://storymaps.arcgis.com/stories/62e633c7685847c0a5474080a276dcec</u>

16
