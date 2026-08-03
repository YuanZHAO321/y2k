---
title: "Practical 3 - Spatial Data Input and Manipulation"
source: "Sophomore/Hilary Term/EART29102/Practical/Week 3/Practical 3 - Spatial Data Input and Manipulation.pdf"
type: pdf
---

_EART29102: Practical 3_

# Practical 3: Spatial Data Input and Manipulation

### Learning objectives

By the end of this practical you will be able to:

- Apply a coordinates system to a raster image (like aerial photographs or scanned maps).

- Georeference an image using control points to connect raster images to their spatial locations on a reference databases such as a basemap.

- Digitise features on a raster image to make feature classes of point, polyline and polygon vector data.

- Add new fields and data to an Attribute Tables of a Feature Class.

## Contents

|**1**<br>**Georeferencing an image**............................................................................................................... 2|
|---|
|1.1<br>Download and add the geological map image ........................................................................ 2|
|1.2<br>Apply a projected coordinate system ...................................................................................... 3|
|1.3<br>Add control points to georeference the image ....................................................................... 4|
|1.4<br>Fitng method and errors ....................................................................................................... 7|
|**2**<br>**On-screen digitsing**........................................................................................................................ 8|
|2.1<br>Create a new Feature Class ..................................................................................................... 8|
|2.2<br>Adding Features ...................................................................................................................... 9|
|2.3<br>Viewing and adding Feature class atributes ........................................................................ 11|
|**3**<br>**Challenge Exercise (to be completed for homework)**................................................................. 12|
|**4**<br>**Further help**.................................................................................................................................. 12|

Some of this this Practical is based on the resources in Zhu X. (2016) GIS for Environmental Applications, Chapter 3. This is the course textbook and accessible from the Blackboard site.

1

_EART29102: Practical 3_

## 1 Georeferencing an image

#### 1.1 Download and add the geological map image

To follow this example, start a Web browser on your computer, and then download the scanned 1:250,000 geological map of Southwest Tasmania from the Geoscience Australia Portal at <u>htps://portal.ga.gov.au. To find the map, select “Layers” -> “Filters” -> “Keywords” -> “Australian</u> Geological Survey Organisations Network (AGSON)”. Then in the search bar search for “Scanned 1:250,000 Geological Map” and the map should be the first item. Click this to open the drop down and then click “Add to Map”

Select the grid square in south-west Tasmania (south of Australia). This opens the “Inspection Tool” window, from which you can download map as a jpeg (with either 125 dpi or 250 dpi resolution) and save it as sk5505_sk5507.jpg to the directory or folder of your choice. All the scanned geological maps available from the portal are not georeferenced. They can be downloaded free of charge.

Start Arc GIS Pro with a new map.

Click on the **Add Data** button symbol to add sk5505_sk5507.jpg to the view. Click **Yes** to **Calculate statistics** when prompted.

2

_EART29102: Practical 3_

The scanned map is added. There are no coordinates for the image so it is unlikely to appear on the world map

If it is not visible in the **Map View** then right click the layer and select **Zoom to Layer**

#### 1.2 Apply a projected coordinate system

The georeferencing system of the map is printed on the map image.

The map coordinate system is GDA94 MGA Zone 55.

In the **search box** (top of the ribbon) or in **Tools** type **Define Projection.** Select sk5505_sk5507.jpg as the **Input Dataset or Feature Class** . For the **Coordinate System** , click

the **globe** button and click the **Coordinate Systems** tab.

Expand **Projected Coordinate Systems** > **National Grids** > **Australia** , and then select GDA 1994 MGA Zone 55.

Click **OK** and **Run.**

3

_EART29102: Practical 3_

To check that your image has the correct coordinate system:

In the **Contents Pane** , select the sk5505_sk5507.jpg layer and right-click **Properties** > **Source** > **Spatial Reference** and check the coordinate system is GDA 1994 MGA Zone 55

#### 1.3 Add control points to georeference the image

Notice that on the Southern Tasmania geological map, the MGA x and y coordinates are marked at regular intervals along the map border: x coordinates (eastings) along the top and bottom, and y coordinates (northings) down the left and right sides. MGA is a grid reference system. The + marks on the map represent the grid reference lines every 10,000m, which can be used to assist in finding the x and y coordinates of a location. By using the grid reference lines, the x and y coordinates of:

lower left corner are 270,000m (east) and 5,140,000m (north);

lower right corner are 460,000m and 5,140,000m;

upper right corner are 460,000m and 5,380,000m;

upper left corner are 270,000m and 5,380,000m.

These will be used as control points for georeferencing.

4

_EART29102: Practical 3_

In the **Contents Pane** , right-click the layer sk5505_sk5507.jpg and select **1:1 Zoom To Source Resolution** . This will give you the optimal display to locate a control point.

Click **Imagery** on the main menu bar and click the **Georeferencing** button to display a new menu.

On the Georeferencing toolbar, click **Auto Apply,** this automatically moves the display of the image to its real-world location based on the coordinates you enter.

Click the **Add Control Points** tool on the Georeferencing toolbar. The shape of the mouse pointer changes to a crosshair when you move it over the map display.

Note that you will need to pan and zoom around the map so to do this while in georeferencing you can press and hold the “c” key to do this. Be patient, it takes a little practice!

Press “c” and pan the map so that you can see its lower left corner – the first control point. Position the crosshair over the point, then click. This enters a control point.

Right-click anywhere in the view, and select Input X and Y. . . .

In the Enter Coordinates dialog, enter 270000 for X (easting) and 5140000 for Y (northing).

5

_EART29102: Practical 3_

Click **OK.** The image display is moved to real-world coordinate space.

(Note that **DMS** in the **Target Coordinates box** is Degrees, Minutes, Seconds, in our example we are using UTM coordinates).

In the **Contents Pane** , right-click sk5505_sk5507.jpg, and click **Zoom To Layer** to redisplay the scanned map.

Press and hold “c” and Pan and Zoom in on the lower right corner of the map and add the second control point. Then repeat to add the other two control points to your map.

6

_EART29102: Practical 3_

#### 1.4 Fitting method and errors

Click the Control Point button on the Georeferencing toolbar. In the window, a table of links (between source and georeferenced control points) and errors is shown. Each row contains the from (source)–to (map) coordinates for one control link and residuals (errors). The residual error (in metres) is computed for each link by comparing the actual location of the map coordinate to the position in the source image. The average discrepancy for all links is expressed as the Residual (RMS root mean square). The scanned map is transformed using the default 1st Order Polynomial (Affine) transformation method. The values in your link table will likely differ from those shown in the image below. The smaller the residuals, the better the outcome, ideally the RMS should be <10m.

If you make a mistake you can uncheck or remove a control point or update its values in the table.

Challenge 1: Add a total of eight control points and change the fitting to a 2<sup>nd</sup> Order Polynomial, hopefully the RMS value should decrease.

When georeferencing is complete click **Save** on the georeferencing menu and **Exit Georeferencing.**

**The following step is not recommended. Not recommended for this exercise (it may take a long time):**

To make the changes permanent click **Save as New** and then **Export Raster as a new tiff layer** and the map image is permanently transformed to its real world location.

7

_EART29102: Practical 3_

## 2 On-screen digitsing

For this example use the geology map of Southwest Tasmania georeferenced in the previous section. Follow the procedure below to extract the lake features from that map using on-screen digitising.

#### 2.1 Create a new Feature Class

Open **Tools** on the **Analysis** tab, and search for **Create Feature Class** in the **Geoprocessing** pane. This creates a new feature class to store the features to be created by digitising.

In the **Create Feature Class** dialog box:

For **Feature Class Location** , browse to the folder containing your Tasmania project, then click **Add** .

Name the **Feature Class** as **lakes** .

Set the **Geometry Type** to **POLYGON** (the default).

For Coordinate System, click the **Spatial Reference Properties** . In the Spatial Reference Properties dialog, browse to **Projected Coordinate Systems** > **National Grids** > **Australia** , and select GDA 1994 MGA Zone 55. Click Add.

8

_EART29102: Practical 3_

<!-- Start of picture text -->
V<br><!-- End of picture text -->

Click **Run** . The new, empty feature class lakes is created and added to the table of contents.

#### 2.2 Adding Features

Zoom in on Lake St Clair in the upper-right part of the map.

Click the **Edit** tab and **Create** , a new window **Create Features** opens and the vector layer **Lakes** is listed

In the **Create Features** window, click the layer name **lakes** in the upper section of the window. A number of construction tools appear in the lower section of the window. Click the **Polygon** tool.

Select points along the boundary of Lake St Clair which can best approximate the shape of the lake. Click once to add each vertex while tracing the boundary of the lake. Press and hold the “c” key to pan and zoom as you draw around the outline. Each green dot represents a vertex. To create smoother curves, add more vertices. After the final vertex is added, double-click at

9

_EART29102: Practical 3_

the start point (or right click **Finish** ). A polygon representing the lake is created as the symbol of a lakes feature.

Click **Finish** to exit and **Save** your Project

Challenge 2: Repeat the above steps to digitise Lake King William.

Challenge 3: Create two more feature classes: one called “Strike_dip” to create points where you see strike dip symbols on the map (click on about 10 of these in a small area of the map); and another feature class called “Faults”, create polylines and trace some of the simple points on the map.

10

_EART29102: Practical 3_

- 2.3 Viewing and adding Feature class attributes

Right click Lakes feature class and select **Attribute Table** . The **Attributes window** opens and appears

below the **Map view** . Three attributes are listed in the window for the digitised lake: ObjectID, Shape, Shape_length and Shape_Area. They are three fields in the attribute table created by the system for the layer lakes.

Now open the **Attribute Table** for Strike_dip feature class. We will add the dip values to the attribute table:

Click the **Add Field** button , a new table appears called **Fields: Strike_dip** . Add a new Field and set it up as follows:

Now Save this new Field, in **Fields** tab, **Changes** group, click **Save** .

The new empty Field appears in the Strike_dip Attribute Table and can be edited with the dip values on the map (you can highlight or flash the point to identify, by selecting the row corresponding to that point). The completed Attribute Table will be like the one below.

Now close your Attribute Tables (save any changes if prompted)

**Save** your project.

11

_EART29102: Practical 3_

## 3 Challenge Exercise (to be completed for homework)

Download the file Manchester.jpg from the Practical folder on the Week 3 Blackboard site. Manchester.jpg is an image of the University Buildings on Oxford Rd, the circular University Place building is at the top centre of the image, with the Williamson Building the adjoining green topped building.

Open a new ArcGIS Pro project and add data from ArcGIS Online - OS Open Background and then add the Manchester.jpg file as a new layer.

See if you can georeference the image to the map as shown below.

_Hint 1_ : you can use the Set SRS (Spatial Reference System) button on the **Georeference** menu to make the image coordinate system the same as the OS Open Backgrounds layer = British National Grid).

_Hint 2_ : you can use the locate button on the **Georeference** menu to search for the University of Manchester to help you locate the correct area on the OS Open Background layer

_Hint 3_ : switch the layers visibility on and off to help you locate control points – rather than using map coordinates, you will have to use geographical features to match between the image and map. The corners of building are good places to use for control points. You will probably need about 6 control points to get a RMS <5 meters).

## 4 Further help

The fundamentals of georeferencing are covered in ESRI training: Georeferencing Raster Data Using ArcGIS – worth reading through once you have completed this exercise.

<u>htps://www.esri.com/training/catalog/57630437851d31e02a43f273/georeferencing-raster-data-</u> - <u>using arcgis/</u>

12
