---
title: "Practical 7 - Wind turbines"
source: "Sophomore/Hilary Term/EART29102/Practical/Week 7/Practical 7 - Wind turbines.pdf"
type: pdf
---

_EART29102 Practical 7_

# Practical 7: Locating the optimal positions of wind turbines

### Learning outcomes

By the end of this practical you will be able to:

- Use spatial analysis tools to merge and extract data need for a project.

- Work with DEM and create viewsheds.

- Know how to use GIS to identify potential sites suitable for wind farms and assess their visibility from nearby locations.

## Contents

|1|Introducton .................................................................................................................................... 2|
|---|---|
|2|Data used in this exercise ................................................................................................................ 2|
|3|Extract relevant data into new feature layers ................................................................................. 2|
|4|Criteria for site selecton ................................................................................................................. 7|
|4|.1<br>Adding Bufers ....................................................................................................................... 7|
|4|.2<br>Merge layers .......................................................................................................................... 8|
|4|.3<br>Change the base map for improved visualisaton ............................................................... 10|
|5|Locaton of existng wind turbines ................................................................................................ 10|
|6|Create a hill shade of the DEM ...................................................................................................... 11|
|7|Locatng the wind turbines ........................................................................................................... 12|
|8|Construct a viewshed using existng wind farm locatons ............................................................ 13|
|9|Resources ...................................................................................................................................... 15|

1

_EART29102 Practical 7_

## 1 Introduction

Wind turbines are seen as a good source of clean energy. After the initial cost of installation, a turbine can be expected to last between 20 – 25 years. Modern turbines are typically between 25 – 80 metres high with a rotor diameter of up to 65m. They are large structures in the landscape which can be seen for many miles.

For the best performance, wind turbines are typically placed in windy places such as the top of valleys, ridges and offshore. Some people see wind turbines as “blots” on the landscape, considering them as noisy and unattractive structures. Despite being green energy they are not welcomed in areas of outstanding natural beauty such as national parks or sites of special scientific interest and due their immense size they can potentially be very hazardous for low flying aircraft and migratory birds.

With so many objections to consider, GIS is an ideal tool for helping a company to locate an optimal site which maximises the energy output whilst considering the wishes of local people and other organisations.

In this exercise you are a manager of a wind farm company looking to a new wind farms in Cornwall, UK. You will use a mixture of data to locate sites and a DEM to calculate a viewshed. A viewshed is a spatial layer indicating which areas are visible to a known location. From this you can identify which towns are able to see a new wind farm and with this knowledge you can tailor any advice given to these populations.

## 2 Data used in this exercise

Start a new ArcGIS project and then search and add the following shape files from ArcGIS online:

Areas of Outstanding Natural Beauty (England) – shape file

Site of Special Scientific Interest (England) – shape file

Built Up Areas (December 2022) Boundaries GB BGG – shape file

Counties and Unitary Authorities (December 2021) Boundaries UK BFE

OS Open Rivers

OS Open Roads

Turn the layers off and on in the **Contents Pane** to show their individual content.

We do not need data for the whole of the UK so the first task is to select and extract data for just the county of Cornwall.

## 3 Extract relevant data into new feature layers

We will start by extracting the county boundary of Cornwall from the **Counties and Unitary Authorities (December 2021) Boundaries UK BFE** layer and making a new feature class layer.

Right click and open the **Attribute Table** for this layer, note the field (column) title containing the county names – CTYUA21NM.

2

_EART29102 Practical 7_

From the **Ribbon** select **Map** > **Select by Attributes** and add the **Expression** as below.

Click **Run** and the county of Cornwall is selected.

3

_EART29102 Practical 7_

Right click the layer **CTYUA_DEC_2021_UK_BFE** and **Selection** > **Make layer from Selected Features.**

Rename your new layer **County_Boundary** then make a new **Group Layer** (by right clicking **Map** in the **Contents Pane** ), name your new layer **Cornwall** and place your **County_Boundary** layer into this group.

You can now remove the **Counties and Unitary Authorities (December 2021) Boundaries UK BFE** layer from your map.

You will use this layer as a boundary for all your other layers: lets extract all the roads in Cornwall from OS Open Roads.

Select **Map** > **Select by location**

**Input Features** > **OS Open Roads** (Road Link)

**Relationship** > **Intersect**

**Selecting Features** > **County_Boundary**

4

_EART29102 Practical 7_

Expand **OS Open Road** group layer and right click **Road Link.**

Then **Selection > Make layer from selected features**

Rename the new output layer to **Roads** move it to the group layer **Cornwall** and remove the **OS Open Rivers** from your project.

Now repeat this for the remaining FOUR layers using the **Relationship** shown in the Table below:

|_Input Features_|_Relatonship_|_New output layer name_|
|---|---|---|
|OS Rivers|Intersect|Rivers|
|Areas of OutstandingNatural Beauty|Have their center in|AONB|
|Sites of Special Scientfc Interest|Within|SSSI|
|Built Up Areas (December 2022)<br>Boundaries GB BGG|Within|Urban_Areas|

After creating the new layers **remove** the parent layers from your project.

Move the new output layers into the **Cornwall** layer group.

Following this your map should be similar to below with all data confined to the boundary of Cornwall:

We have a dense road network so let’s consider that only A and B roads are important for siting turbines (and note there are no Motorways in Cornwall). So let’s select and extract theses roads.

5

_EART29102 Practical 7_

Select **Map** > **Select by Attributes** then **Input Rows** as **Roads** and add the following two expressions.

Click **Apply** and then **OK** and make a new layer from the selection called **RoadsA_B** you can now remove the parent layer **Roads** from your project.

Note: If the blue text , if records to be processed = 0 or 1 then you need to **Clear** selected features first i.e.

###### **Map** > **Selection** group > **Clear**

The new version of your map shows only A roads (in red) and B roads (in green).

6

_EART29102 Practical 7_

**Save** your project.

## 4 Criteria for site selection

The final site selection must consider that a wind turbine cannot be within:

100m of a road or river

500m of a built-up area, or an Area of Outstanding Natural Beauty (AONB), or a Site of Special Scientific Interest (SSSI).

#### 4.1 Adding Buffers

Our first criteria is that wind turbines cannot be within 100m of a road. We can, therefore, start by creating a 100m buffer around the Roads layer.

Use the **Pairwise Buffers** geoprocessing tool in the **Analysis** > **Tools** .

Now repeat by adding buffers for the other layers of interest: River (100 m buffer), Urban_Area (500 m buffer), SSSI (500 m buffer) and AONB (500 m buffer).

Create a **New Group Layer** , named it **Pairwise_Buffers** and place all of your buffer layers into this group layer.

With only the **Pairwise_Buffer** layers visible then your map will look similar to the one below. Note: I have changed the colour scheme to be the same for all layers.

7

_EART29102 Practical 7_

The map shows all the areas in Cornwall where planning laws prevent the construction of wind turbines.

#### 4.2 Merge layers

Now let’s combine all the buffers together to create a single layer.

Search for the **Merge** geoprocessing tool and add the **Input Datasets** as below.

Name the **Output Dataset** as **No_Build,** click **Run**

8

_EART29102 Practical 7_

Now we have a single layer where the siting of wind turbines is excluded.

Now let’s create a new layer where it may be possible to build the turbines. We are going to subtract the No-Build areas from the County_boundary to achieve this.

Search for the **Erase** geoprocessing tool and enter **Input Features** and **Erase Features** as below, name your **Output Feature Class** as **Build**

Now turn off the visibility of the No_Build layer and your map should be similar to below showing you all possible places to site wind turbines (shown in pink on my version).

9

_EART29102 Practical 7_

#### 4.3 Change the base map for improved visualisation

The map can be made more useful if we add ariel imagery as our basemap.

Change the **Basemap** to **Imagery** ,

It helps to change the **transparency** of the **Build layer** (to about 50%) to improve visibility of the map.

Zoom in and out, pan around and inspect the likely sites for siting wind turbines.

## 5 Location of existing wind turbines

You can compare existing wind farm locations in Cornwall by adding from ArcGIS Online the layer **Onshore_Windfarms** .

Expand the layer to see the legend for this map. Green dots are existing sites.

If you zoom right-in to the green points and click on them you can find out a bit more information. You should also be able to see the actual turbines by zooming-in on the imagery layer.

**Challenge Q1:** What type of land use covers most of the potential site areas you have identified?

**Challenge Q2:** The highest wind speeds are likely to be close to the coast, how much  of the coastal area is available for wind turbine developments?

**Challenge Q3** : Apart from those considered already, what other factors may influence the siting of wind turbines?

**Challenge Q4:** How do the locations of existing wind turbines compare with your map of possible areas to site wind turbines? Are there any anomalies?

10

_EART29102 Practical 7_

- 6 Create a hill shade of the DEM

A DEM raster has been created for you. It is based on the OS Terain 5m reolution DEM for the UK. If you need any data like this, which is not publicly available and therefore not on Arc GIS online, then you can be downloaded from Digimap.

###### **Add Data** from **ArcGiS online** > **My Organisation** > **DEM_StCM**

(it is also on the Canvas site (week 7)).

The raster file contains elevation data for the area around the village of St Columb Major (town with a population of about 4,500 people) in Cornwall.

Remember light areas are high elevation, dark areas are low elevation You may want to change the display of the DEM layer.

Right-click the **DEM_StCM** layer in the **Contents** pane and choose **Symbology** .

##### Expand **Primary Symbology** and select **Shaded Relief**

Set the **Colour scheme** , the colour ramp shown below is particularly effective at displaying elevation data.

Your map should look something like this:

11

_EART29102 Practical 7_

## 7 Locating the wind turbines

You are now ready to locate some turbine sites. Each point you identify represents a single wind farm. A single farm can have more than one turbine but as a first pass, you are simply interested in identifying the general farm location.

Each wind farm you identify must be in an area you have identified in the “Build” layer and it must not be near another wind farm

Let us create a new point map layer to store these locations.

Use the **Create Feature Class** by searching in the **Geoprocessing Pane** .

Use a suitable **Feature Class Name** e.g. turbines.

Set the **Coordinate System** to **DEM_StCM** layer this should be **British national Grid.**

Set the **Geometry Type** to **Point** and click **Run.**

You should now see a new point feature class (turbines) appear in the Contents Pane. We now need to add some points to this new feature class. To do this, we need to start editing the turbines map layer:

Select **Edit** > **Create** .

You should now be able to add points representing turbines by selecting point tool and digitising on screen.

Digitise the two existing turbines (green points from the Onshore_Windfarms layer) to the north of St Columb Major.

Click **Save** on the ribbon to save your edits.

You may find that the last point you digitised is still selected, so to clear the selection, you can right-click on the **turbines** layer in **Contents Pane** , choose **Selection** and then **Clear**

12

_EART29102 Practical 7_

**Selection** (if you do not clear the selection, then if you run any tools subsequently, only the selected point will be used for analysis).

## 8 Construct a viewshed using existing wind farm locations

Now we need to calculate the area from which the new turbines will be visible.

From the **Geoprocessing Pane** search for the **Geodesic Viewshed** tool.

Select **DEM_StCM** as your **Input raster** and **turbines** as your **Input point or polyline observer features** .

Give the **Output Raster** an appropriate name, such as **viewshed_DEM1** .

###### _Viewshed Parameters_

- The **refractivity coefficient** is used in specialist applications involving non-visible parts of the spectrum, such as siting mobile phone masts. We can ignore it.

13

_EART29102 Practical 7_

- The **Analysis method** gives two options: all sightlines, the default, which we will use here, or perimeter sightlines, a much quicker but less accurate calculation that works out which pixels along the study area perimeter are visible, radiating these back to observer features.

- The **Analysis type Frequency** setting means that the number of visible observer points will be calculated.

- Notice also the **Vertical error** setting. If we knew the Root Mean Square Error (RMSE) of the elevation values in our DEM, it could be incorporated into viewshed calculations via this setting.

###### _Observer Parameters_

- **Surface offset** will ‘raise’ the surface of the DEM by a given amount. Enter **1.6** for this as an approximate height in metres of somebody standing in the landscape.

- **Observer offset** raises the surface where the wind turbines are present. Since our turbines are 25 metres tall, enter **25** here (yes – it is a bit confusing that the software terms our turbines ‘observer points’). Note that **Observer elevation** enables us to set the height of our turbines as an absolute elevation value above sea level – not what we want to do here.

- The **Radii** settings can be used to limit the viewshed calculations to just part of a study area, but we will not use them here.

Click **Run** (be patient this may take some time, as the calculations are fairly computerintensive).

Use the ‘explore’ tool on the **Map** menu ribbon to investigate the output.

You should now see the areas from which your proposed turbines are visible

The final map will look similar to the one below. It shows that one of the two existing wind farms (pins) are visible in parts of the village of St Columb Major.

The resultant raster grid indicates how many of the input features (wind turbines) are visible from each grid cell. A value of ‘no data’ (blank areas on the map below) means that the grid cell cannot be seen by any of the turbines, a value of one (yellow areas) means that the grid cell is visible from one turbine, two (brown areas) means that the grid cell is visible from two turbines, and so on.

14

_EART29102 Practical 7_

**Challenge Q5:** The viewshed you created shows that one of the winds farms is visible in St Columb Major. Work out a method of determining which one of the wind farms this is.

**Challenge Q6:** Now modify your turbines point layer to include a proposed new wind farm site south of St Columb Major. Use your Build layer to help identify this site. Run a viewshed analysis to determine if your proposed wind farm will be visible from the village.

**Homework challenge** : Add to your **Project** the feature layer from ArcGIS online: **Feasibility Map_WFL1** it has a more comprehensive assessment of renewable energy locations in Cornwall. It is interesting to compare feasible area for wind farms with your own version. It also includes locations of solar photovoltaic farm locations.

## 9 Resources

<u>Where is it suitable to build wind turbines? A good example using ArcGIS online.</u>

15
