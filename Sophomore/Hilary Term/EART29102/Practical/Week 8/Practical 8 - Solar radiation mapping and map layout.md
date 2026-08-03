---
title: "Practical 8 - Solar radiation mapping and map layout"
source: "Sophomore/Hilary Term/EART29102/Practical/Week 8/Practical 8 - Solar radiation mapping and map layout.pdf"
type: pdf
---

_EART29102 Practical 8_

# Practical 8: Solar radiation mapping and map layout

### Learning outcomes

By the end of this practical you will be able to:

- Estimate solar energy production for an area of Greater Manchester.

- Apply surface parameters to exclude unfavourable aspect and roof slopes.

- Be able to produce an effective map layout.

## Contents

|1<br>Introducton .................................................................................................................................... 2|
|---|
|2<br>Download the data .......................................................................................................................... 2|
|3<br>Create a hillshade efect .................................................................................................................. 3|
|4<br>Explore building footprints .............................................................................................................. 3|
|5<br>Map solar energy ............................................................................................................................ 3|
|6<br>Convert the units of measurement ................................................................................................. 5|
|6.1<br>Electricity generaton in context ............................................................................................. 6|
|6.2<br>Create a slope layer ................................................................................................................. 7|
|6.3<br>Create an aspect layer ............................................................................................................. 8|
|6.4<br>Remove roofs with high slopes ............................................................................................... 9|
|6.5<br>Remove roofs that face north ................................................................................................. 9|
|7<br>Map layout .................................................................................................................................... 11|
|7.1<br>Hints and tps ........................................................................................................................ 11|

##### **Data sources used in this tutorial:**

Digital terrain model (1m resolution) htps://environment.data.gov.uk/survey

OS OpenMap Local Buildings –for building footprints

Manchester Ward Boundaries – used to obtain Burnage boundary as a mask for buildings and the DTM raster.

_This practical is adapted from the Arc GIS Pro tutorial: Estimate Solar Power Potential_

https://learn.arcgis.com/en/projects/estimate-solar-power-potential/

1

_EART29102 Practical 8_

## 1 Introduction

Your nonprofit organization recently launched a pilot program to encourage the residents of Burnage, a mainly residential area of Manchester, UK, to install solar panels on their roofs. The goal is for the solar panels to produce a large part of the electric power consumed by each household.

In this practical, you will use ArcGIS Pro to determine how much solar radiation each rooftop in Burnage receives throughout the year. Then you will produce an effective output of your results to as part of a report for your organisation.

## 2 Download the data

Start a new ArcGIS project and then from Blackboard download and open the ArGIS Pro map package **Burnage.mpkx** . When opened, you should see the following files:

**Burnage_DTM_1m** – a geotiff file

**Burnage Local Buildings** – a vector data file containing the footprint of residential buildings **Burnage_outline** – a vector data file containing the outline of the Burnage area.

Turn the layers off and on in the **Contents Pane** to real their individual content.

The **Burnage_DTM_1m** layer represents an area of Burnage as a digital terrain model (DTM). A DTM shows the elevation of the ground and the features on the ground, such as buildings and trees. This DTM is a raster layer, which depicts data in a grid where each cell contains a numeric value. It is symbolized so that darker grey cells have lower elevations and the lighter grey and white cells have higher elevations. In this raster, each cell represents a surface of 1 x 1 meters.

2

_EART29102 Practical 8_

## 3 Create a hillshade effect

Although patterns in the DTM suggest the locations of buildings and vegetation, you can better visualize the surface by creating a hillshade effect. A hillshade raster layer uses a realistic shading effect to depict elevation.

In the geoprocessing pane search for the **Hillshade** tool, using the default setting, create a hillshade and name it **HillShade_DTM_1m** .

For optimum visual effect, you can combine hillshade and DSM layer symbolization.

In the **Contents** pane, drag the DTM layer above the **Hillshade_DTM_1m** layer.

Set the DTM layer to 40 percent layer transparency. When it is drawn above the hillshade, both layers are visible.

## 4 Explore building footprints

The project contains a layer called **Burnage_Local_Buildings** which contains outlines of every building in Burnage. Unlike the DTM and hillshade layers, which are rasters, this is a vector layer, which displays spatial information in the form of polygons.

Zoom and pan throughout the map to explore the Burnage area.

You can see that there are many types of buildings, from family houses to larger commercial and school buildings. Some areas also contain trees which can have an impact on solar power production.

## 5 Map solar energy

Next, you'll create a raster layer that maps how much solar energy reaches rooftop surfaces in Burnage over the course of a typical year. The more solar energy a roof surface receives, the more electric power could be generated if it were equipped with solar panels.

To create the solar radiation layer, you'll use the **Area Solar Radiation** tool. This tool is part of the **ArcGIS Spatial Analyst extension** and uses a DTM as input. It calculates radiation based on a sophisticated model that takes into account the position of the sun throughout the year and at different times of day, obstacles that may block sunlight such as nearby trees or buildings, and the slope and orientation of the surface.

The DTM provides the necessary information on obstacles, orientation, and slope. The output will be a raster layer where each cell value is the amount of solar radiation in watt-hours per square meter (Wh/m<sup>2</sup> ) at that location.

_Note: The Area Solar Radiation tool is computationally intense and may take about 10 minutes to run._

On the ribbon, on the **Analysis** tab, in the **Geoprocessing** group, click **Tools** .

The **Geoprocessing** pane appears.

Search for and open the **Area Solar Radiation** tool.

3

_EART29102 Practical 8_

In the **Area Solar Radiation** tool, for **Input raster** , choose **Burnage_DTM_1m** . For **Output global radiation raster** , change the output name to **Solar_Rad** .

When the input raster is chosen, the **Latitude** parameter is automatically populated with the latitude of the DTM. This parameter helps determine the sun's position.

By default, the tool runs using an interval of several days. You will change the time interval to compute the solar radiation over the course of an entire year.

For **Time configuration** , choose **Whole year** . If necessary, for **Year** , type **2024** .

By default, the tool computes the amount of solar radiation once every half hour for each day sampled. For **Hour interval** , type **1** (i.e. once every hour) to reduce calculation time.

By default, the tool checks 32 directions around each cell to find light-blocking obstacles. To reduce calculation time change this value to 16. Expand **Topographic parameters** . For **Calculation directions** , type **16** .

You will also use the **Burnage_Local_Buldings** layer as a mask, so that only areas within the building footprints will be processed, again saving calculation time. Click the **Environments** tab. Under **Raster Analysis** , for **Mask** , choose **Burnage_Local_Buldings** .

4

_EART29102 Practical 8_

Click **Run** .

## 6 Convert the units of measurement

The solar radiation raster uses watt-hours per square meter as its unit of measurement (Wh/m<sup>2</sup> ). According to the legend in the Contents pane, some cells have values of over 1 million Wh/m<sup>2</sup> . To reduce the size of these values and make them easier to read, we will convert the raster layer to kilowatt-hours per square meter (kWh/m<sup>2</sup> ).

You won't need the **Burnage_Local_Buildings layer** for the next steps, so turn it off.

In the **Geoprocessing** pane, search for and open **Raster Calculator (Spatial Analysis Tool)** .

There are 1,000 watts in a kilowatt, so to convert the units of measurement, you need to create an expression that divides existing cell values by 1,000.

In the **Raster Calculator** tool, for **Map Algebra** expression, type (or build) the following expression:

"Solar_Rad" / 1000

For **Output raster** , change the output name to **solar_rad** .

Click **Run** .

5

_EART29102 Practical 8_

The new raster layer is created and added to the map. It is similar to the original solar radiation layer, but the values are 1,000 times smaller.

You no longer need the original solar radiation layer, so you can remove it.

#### 6.1 Electricity generation in context

The estimated solar power is between about 500-1000 kWh/yr. A typical household solar panel system can only convert between 10-20% of this energy into electricity, so assuming a conversion of 17%, then the estimated potential electricity generation for a rooftop with 800 kWh/m<sup>2</sup> reduces to 800 × 0.17 = 136 kWh/m<sup>2</sup> .

A typical household solar panel system has a maximum capacity of 3.5 kW electricity output. The UK has an average of 5 hours sunlight every day of the year, this translates to 3.5 × 5 = 17.5 kWh per day. A typical system also requires about 28 m<sup>2</sup> of roof space, so this means the energy output is 17.5/28 = 625 Wh/m<sup>2</sup> each day. Compare this to the value of incoming solar radiation above – note the different scale units (kW versus W). These estimates are for solar panel systems in perfect, optimal conditions, for the maximum possible output. In reality systems produce more like 200 to 300 Wh/m<sup>2</sup> each day.

There are some other factors that affect the amount of solar radiation the surfaces of rooftops will receive e.g. orientation, weather, pitch, efficiency, shading. Let’s consider a couple of these in our ArcGIS project:

1. Suitable rooftops should have a slope (pitch) of 45 degrees or less, as steep slopes tend to receive less sunlight. To determine rooftop slope, you must create a slope raster layer. Note that flat roofs are suitable for solar panels.

6

_EART29102 Practical 8_

   2. Suitable rooftops should not face north, as north-facing rooftops in the northern hemisphere receive less sunlight. To determine rooftop orientation, you must create an aspect raster layer.

- 6.2 Create a slope layer

First, you will use the **Surface Parameters** tool to create a slope raster layer based on your DTM.

In the **Geoprocessing pane** , search for and open the **Surface Parameters (Spatial Analyst Tools)** tool, and enter the following parameters:

For **Input surface** raster, choose **Burnage_DTM_1m** .

For **Output raster** , type **Slope_DTM** .

Confirm that **Parameter type** is set to **Slope** .

In the **Environments** tab, then **Raster Analysis** set **Mask** to **Burnage_Local_Buildings.**

Click **Run** .

The tool runs and the new raster layer is added to the map.

7

_EART29102 Practical 8_

Each cell in this layer contains a slope value ranging from 0 to 90 degrees. The lighter colours represent steeper slopes while darker colours represent milder slopes.

#### 6.3 Create an aspect layer

To determine the rooftop orientation, you will create an aspect raster layer, again using the **Surface Parameters** tool.

In the **Surface Parameters** tool pane, enter the following parameters:

For **Input surface raster** , keep **Burnage_DTM_1m** .

For **Output raster** , type **Aspect_DTM** .

For **Parameter type** , choose **Aspect** .

For **Environments** > **Raster Analysis** > **Mask** use **Burnage_Local_Buildings**

Click **Run.**

The tool runs and the new raster is added to the map.

8

_EART29102 Practical 8_

Each cell contains a value expressing orientation in degrees, with 0 representing absolute north and 180 representing absolute south.

#### 6.4 Remove roofs with high slopes

Looking at the legend for the **Slope_DTM** raster there are no slopes steeper than 45 degrees so we do not need remove any cells with values higher than this threshold.

#### 6.5 Remove roofs that face north

The second criterion for suitable rooftops is that roof surfaces should not face north.

Based on the **Aspect_DTM** legend, slopes that face north have a value less than 22.5 degrees or more than 337.5 degrees.

We will use the **Con (Spatial Analyst)** tool to determine roofs that oriented north. The **Con** (conditional) tool allows you to control the output value for each cell based on whether the cell value is evaluated as true or false in a specified conditional statement.

In the **Geoprocessing pane** search for the **Con (Spatial Analyst)** tool.

##### For **Input conditional raster** , choose **Aspect_DTM** .

North-facing slopes are slopes that have a value less than 22.5 or more than 337.5. Your expression will require two clauses to fulfil both of these conditions.

In the **Con** tool pane, for **Input condition raster** , choose **Aspect_DTM** .

9

_EART29102 Practical 8_

Add the new expression **Where VALUE is greater than 22.5** .

Click **Add Clause** . Create the expression **And VALUE is less than 337.5** .

Together, these clauses cover all surfaces that do not face north. These expressions will be applied to every cell in the aspect raster. If a cell has a value less than 22.5 and more than 337.5 degrees then that cell is considered false. If not, the cell is considered true.

Next, you will choose the raster layer that will provide the output cell values for cells found to be true. Ultimately, you want to compute the solar radiation potential of the rooftops, so you'll have the output layer use solar radiation cell values.

Continue entering the following in the Con tool pane:

For **Input true raster or constant value** , select **solar_rad** .

For **Output raster** , type **solar_rad_NN** (NN stands for No North).

Click **Run** .

The new raster layer is added to the map. You may not notice very much visual difference between the **solar_rad** and **solar_rad_NN** rasters but by comparing the legends of these two

10

_EART29102 Practical 8_

layers you can see that some of the lower solar radiation surfaces have been excluded from the solar_rad_NN layer. This is expected because north-facing roof surfaces will receive lower solar radiation levels.

For actual solar panel installation, it would be necessary to look at each rooftop in more detail, but for the purpose of your analysis, this approximation is sufficient.

**Save** your Project.

## 7 Map layout

The map pasted at the end was produced following the instructions using the ESRI tutorial at the link below (there is a video showing you how to do add and change different elements). Use this tutorial to help you to produce an effective map. Make sure you include all the elements required to communicate the purpose and results of your map.

<u>htps://pro.arcgis.com/en/pro-app/latest/get-started/add-maps-to-a-layout.htm</u>

#### 7.1 Hints and tips

1. ArcGIS Pro adds service layer credits to your map, you will probably want to remove these as they tend to make the map too cluttered.

On the **Map Frame** group, **Dynamic text** drop down scroll down the list until you see **Service Layer Credits,** select this and then click on the credits on the map so they are selected (black box).

**Uncheck** the appropriate text box in the contents pane (trial and error may be necessary if you have several text boxes), in the example below unchecking Text 3 removed them.

11

_EART29102 Practical 8_

2. To add a location map you may need to add a new basemap layer. Click on the **Map layer** and select **New Map** > **New Basemap** .

   - I used **GB Light Grey** as the base map for the main map and **World Topographic Map** for my location map.

3. My map shows the solar radiation for south Burnage – I could have made two separate maps covering south and north Burnage or a multi-panel map with south and north on the same page.

4. I did not add a grid to my map but this can be done by clicking on the **Map Frame** in the **Contents pane** and the **Insert** > **Grids.**

12

_EART29102 Practical 8_

5. You can also add your name, student number, date of creation, and further text, etc to enhance your map.

6. To print your map or export it you can **Share** > **Export** in a number of formats. My map was exported as a jpeg image.

13

_EART29102 Practical 8_

14
