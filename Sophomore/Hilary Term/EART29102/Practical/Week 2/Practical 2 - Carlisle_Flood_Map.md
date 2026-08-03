---
title: "Practical 2 - Carlisle_Flood_Map"
source: "Sophomore/Hilary Term/EART29102/Practical/Week 2/Practical 2 - Carlisle_Flood_Map.pdf"
type: pdf
---

_EART29102: Practical 2_

# Practical 2: Carlisle Flood Exercise

## Contents

|1.|Introduction .................................................................................................................................... 2|
|---|---|
|2.|Learning objectives ......................................................................................................................... 2|
|3.|Data Requirements ......................................................................................................................... 3|
|4.|Add Data from ArcGIS on-line ......................................................................................................... 3|
||OS Open Rivers data ........................................................................................................................... 3|
||OS OpenMap Local Buildings vector data ........................................................................................... 3|
|5.|Select a smaller area appropriate for our study ............................................................................. 3|
|6.|Name the Map ................................................................................................................................ 6|
|7.|Query the data ................................................................................................................................ 7|
|B|uffer the river centreline .................................................................................................................. 7|
|C|alculate the number of buildings in the buffer ................................................................................. 8|
|8.|Create a presentation quality map ............................................................................................... 10|
||Display the correct data .................................................................................................................... 10|
|S|tyling ................................................................................................................................................ 11|
|9.|Export your map............................................................................................................................ 12|
|10.|<br>Creating a Layout ...................................................................................................................... 12|
|11.|<br>Further resources ...................................................................................................................... 14|
|12.|<br>Challenge Exercise (to be completed for howework) ............................................................... 15|

This Practical is based on teaching resources provided by the Digimap Resource Centre <u>https://digimap.edina.ac.uk/webhelp/training/gis_exercises/flood_analysis.pdf</u>

Background information on Carlisle flooding in 2015 (this is a professional example of a ArcGIS Story Map, it contains maps, videos and reports).

<u>https://www.arcgis.com/apps/MapSeries/index.html?appid=00d53785d4124453a384e88b7c709ac6</u>

1

_EART29102: Practical 2_

### **1. Introduction**

Carlisle has a long history of flooding. The city is situated on the flood plain of the River Eden and three rivers meet in the city. There was a significant flood in 2005 in which 3 people died and more than 1800 properties were flooded.

The aim of this exercise is to use a selection of Ordnance Survey map data in ArcGIS Pro, to analyse how many properties are at risk of flooding.

### **2. Learning objectives**

By the end of this exercise you will be able to:

- download map data from ArcGIS On-line

- style map data

- create a buffer

- select features by location and save output

- create an effective presentation map

2

_EART29102: Practical 2_

### **3. Data Requirements**

- Detailed vector data showing buildings.

- Vector data showing rivers.

- Raster map for background mapping.

### **4. Add Data from ArcGIS on-line**

#### **OS Open Rivers data**

OS Open Rivers is a free GIS dataset published by the Ordnance Survey showing over 144,000 km of freshwater rivers, tidal estuaries and canals in Great Britain.

From the **Map** tab Click the **Add Data button.**

Navigate to Portal the ArcGIS Online.

Search for OS Open Rivers, select and then click **OK.**

#### **OS OpenMap Local Buildings vector data**

Search ArGIS Online for OS OpenMap Local Buildings and add this dataset to your map.

### **5. Select a smaller area appropriate for our study**

Our rivers and buildings layers covers all of the UK.

Let’s select a smaller area just covering Carlisle. Our map will draw faster with a smaller area.

First, let’s find Carlisle on the map. In the **Map** tab, select **Locate** and in the search box type **Carlisle,** the **Map View** is now centred on **Carlisle**

3

_EART29102: Practical 2_

Your map window should look similar to this image – you can see the rivers, the buildings and World topographic map the map is centred on Carlisle.

**Click Select** on the toolbar.

##### Click **Select by Rectangle.**

Click on your map window.

Draw a rectangle covering the area of Carlisle.

You should see all the data within that box highlighted in blue on your map, like this image:

4

_EART29102: Practical 2_

Now click **List By Selection** in the Table of Contents.

You will see the number of features that have been selected from **OS Open Rivers** and **OS LocalMap Buildings** .

Right click **OS Open Rivers > Selection > Make layer from selected features.**

Now click **List by Drawing Order** in the **Contents Pane** :

You will see a new layer in the Table of Contents – **OS Open Rivers line selection** .

You will have a new rivers layer in your map.

You can uncheck the original **OS Open Rivers** layer.

Now do the same for the **OS OpenMap LocalBuildings** group to create two new layers as shown below.

5

_EART29102: Practical 2_

Finally, we still have features selected. Let’s clear them.

Click **Clear** in the Selection group.

In the **Contents Pane** list the layer by **Drawing Order** and you should have similar to below:

### **6. Name the Map**

Let’s rename our map to **Carlisle Flood Map** .

Select **Map** in the **Contents Pane** and right-click **Properties** > **General** then type the **Carlisle Flood Map** into the **Name** box, OK

6

_EART29102: Practical 2_

### **7. Query the data**

**Question:** How many buildings in Carlisle are at risk of flooding?

##### **To answer this, we need to:**

Define an **AT RISK area** around the rivers, within which buildings could potentially flood. Query **how many buildings lie within the AT RISK area.**

#### **Buffer the river centreline**

Let’s say that any property within 100m of the river will be considered “AT RISK” from flooding.

We can use the river centreline and create a 100m buffer around it.

We will use our **rivers selection** layer.

Open the Buffer tool: **Analysis** → **Buffer** (note: this function can also be found in **Tool Pane** )

Note you may see a tool called **Pairwise Buffer** . This has the same functionality as **Buffer** , just utilises parallel processing to speed up the operation.

Set the **Input Features** to **OS Open Rivers selection** Name it **rivers_buffer100.** Set the **Distance** to **100** and the units to **Meters** . Click **Run.**

7

_EART29102: Practical 2_

A new layer will be created and added to your map. You should be able to see a buffer zone around all the rivers, similar to this image.

#### **Calculate the number of buildings in the buffer**

Now let’s calculate the number of buildings that lie within the buffer we have just created.

##### Choose **Select By Location** from the **Map** toolbar.

Select Input Features **OS OpenMap Local Buildings selection** and **OS OpenMap Important Buildings selection.**

8

_EART29102: Practical 2_

Set **Selecting Features** to **rivers_buffer100** (this is our outline feature - we want to see what

is within it).

Set Selection Features > **Intersect.**

Set **Selection Type** > **Select subset from the current selection.**

Press **OK.**

The features that match our search criteria will now have been selected and will appear highlighted in blue on the map.

Let’s save our selected features as a **new layer.**

Switch table of contents to **List by Selection.**

In my version of the map, 1120 local buildings and 18 important local buildings are selected – **NOTE:** you may have a slightly different number depending on the area you selection.

**Right click** the **OS OpenMap Local Buildings selection** and select **Selection > Make Layer From Selected Features.**

##### Do the same for **OS OpenMap Local Important Buildings.**

Return to List by Drawing order – rename your two new layers (… selection selection) to **Flood Risk local buildings** and **Flood risk important buildings.**

Clear the selected features.

9

_EART29102: Practical 2_

### **8. Create a presentation quality map**

We have done some basic analysis. Let’s make a map that we can export and include in a document, to represent the houses that are at risk of flooding in Carlisle.

Our map needs to show:

- River line

- River buffer

- The buildings within the buffer

- Background mapping for context

**Note** you can change the order layers are drawn by dragging them up and down the Contents pane

#### **Display the correct data**

Zoom to a scale of 1:10000.

10

_EART29102: Practical 2_

Make the layers visible in the **Contents Pane** as shown below **.**

Uncheck everything else in the Table of Contents.

How does our map look? It should look similar to the image below. Note to remove the overlapping regions in the river buffer you can recalculate it selecting **Dissolve all output features into a single feature**

#### **Styling**

Let’s try labelling the **OS Open Rivers selection** layer.

Under **Feature Layer** , click the **Labeling tab** , and click Label

The **Label** used is defined by the **Field** box

You should be able to see a label on the River Eden. To change the size, play around with the options in the **Labeling** tab.

Also play around with the colours to improve the appearance.

11

_EART29102: Practical 2_

### **9. Export your map**

You can export your map in various formats, including image formats (jpg/tiff/png) or a pdf.

### **10. Creating a Layout**

On the ribbon, click the **View** tab. In the Windows group, click **Reset Panes** and for **Mapping (Default)** .

This ensures that the Contents and Catalog panes are open and that other panes are closed.

ArcGIS Pro has two views, **Map** and **Layout** . To produce a printed map, we must switch to the **Layout** view.

Select **Insert** from the ribbon and **New Layout.** Select the preferred page size and orientation.

12

_EART29102: Practical 2_

Insert a New Map Frame selecting the Map of Carlisle you have created.

Draw a rectangle of appropriate size for your map

Use these tools to navigate and zoom in layout view

To pan and zoom your map you need to use the Activate button

13

_EART29102: Practical 2_

In Layout view a **Legend, Grid Lines, North Arrow, Title** and **Scale Bar** can all be added to your map. A simple example of a finished map is shown below. See if you can produce a similar version to this map

### **11. Further resources**

ESRI training course for creating map layouts.

<u>https://www.esri.com/training/catalog/5ce42f0c88c6106da2d52fdc/creating-a-map-layout/</u>

14

_EART29102: Practical 2_

### **12. Challenge Exercise (to be completed for howework)**

The Environment Agency define Flood Alert Areas as being:

“a large expanse of floodplain (up to and including the extreme flood outline which defines the Flood Warning Service Limit), within a catchment, sub-catchment or group of catchments, that is/are at risk from low impact flooding (from main rivers, ordinary watercourses and the sea)."

The main drawback of our analysis is the assumption of the 100m (buffer) flood zone, which does not seem very reasonable for several reasons.

A more realistic dataset of Flood Alert Areas is provided by the Environment Agency and available in ArcGIS Online:

Click the small down-arrow next to the add data button and select **Add Data** from **ArcGIS**

##### **Online**

Search for “UK flood alert” and select **Environment Agency: Flood Alert Areas**

Click **OK** and the Flood Alert areas appear for your area of Carlisle. A new shape file has been added as a layer. This covers the whole of the UK it can be reduced to a smaller area as was done previously for the rivers map.

Now carry out the steps done previously to query how many buildings are in the Flood Alert area (hint: use the EA_Flood_Alert_Areas as your buffer;  I got 1726 buildings), make a new layer in your map.

15

_EART29102: Practical 2_

16

## OCR 补充（原文中无文字层的页面）

_(以下内容由图片 OCR 识别得到，原文件该处无可提取文字；识别可能有误，请对照原件。)_

### Page 16

EART29102: Practical 2

16
