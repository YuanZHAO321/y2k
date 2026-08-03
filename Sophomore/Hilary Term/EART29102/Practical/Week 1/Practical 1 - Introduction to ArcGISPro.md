---
title: "Practical 1 - Introduction to ArcGISPro"
source: "Sophomore/Hilary Term/EART29102/Practical/Week 1/Practical 1 - Introduction to ArcGISPro.pdf"
type: pdf
---

_EART29102 Practical 1_

# Practical 1: Introducing ArcGIS Pro

## Learning objectives

By the end of this practical you will be able to:

- understand the ribbon-based layout and basic tools in ArcGIS Pro

- add data to make a map

- know the difference between vector and raster data structures

- apply some geoprocessing tools to vector data to create hillshade and contour layers

## Contents

|1.|Start ArcGIS Pro ............................................................................................................................... 2|
|---|---|
|2.|Open a Project ................................................................................................................................ 2|
|3.|Explore the Navigate Group in the Map Tab .................................................................................. 3|
|4.|Map scale and coordinates ............................................................................................................. 4|
|5.|Adding and removing spatial datasets ............................................................................................ 4|
|6.|Vector data ...................................................................................................................................... 5|
|7.|Raster data ...................................................................................................................................... 7|
|8.|Change the Name of the Map ....................................................................................................... 10|
|9.|Save the Project ............................................................................................................................ 10|
|10.|Improving the look of the raster layer ...................................................................................... 10|
|11.|Convert the raster layer to contour lines (vectorisation) ......................................................... 12|
|12.|Set Map Extent .......................................................................................................................... 12|

This Practical is based on Bajjali, W. (2023). Introduction to ArcGIS Pro. In: ArcGIS Pro and ArcGIS Online. Springer Textbooks in Earth Sciences, Geography and Environment. Springer, Cham. https://doi.org/10.1007/978-3-031-42227-0_1

1

_EART29102 Practical 1_

## 1. Start ArcGIS Pro

To start ArcGIS Pro you must be licensed as a name user and have an account with ESRI. If you are a student, a user account will have been created for you. Each user must have a login name and password (see information in Lecture 1 handout).

The first time you start ArcGIS Pro, you must enter your ArcGIS online by typing in any browser <u>www.arcgis.com “Sign In” use your login name and password. Signing in to your organization</u> (University of Manchester - Uomanchester) also allows you to access your content, group content, and your organization’s content in your project . You can sign-in to additional portals to use their content as well. You must also sign-in to publish and share with your organization.

## 2. Open a Project

Launch ArcGIS Pro and log in using your account.

### Under **New Project** click **Map.**

ArcGIS Pro opens with an interface and consists of the following:

1. Ribbon

2. Views

3. Panes

<!-- Start of picture text -->
Ribbon<br><!-- End of picture text -->

<!-- Start of picture text -->
Contents<br>Pane<br><!-- End of picture text -->

<!-- Start of picture text -->
Map<br>view<br><!-- End of picture text -->

<!-- Start of picture text -->
Catalog<br>pane<br><!-- End of picture text -->

2

_EART29102 Practical 1_

**Ribbon:** The ribbon at the top of the application window displays and organizes functionality into a series of tabs. Some of these tabs (core tabs) are always present. Others (contextual tabs) appear when the application is in a particular state.

**Catalog View:** Catalog View is in the middle of the program and consists of map view. The map view is a window that displays a map. Every view has a tab that can be used to close the view or drag it to a different position. A project may have many views, which can be opened and closed as needed. The tab of the active view is blue.

**Panes:** There are three panes, and all are dockable windows. The first pane is called the **Contents pane** (left), which displays the contents of a view. The second pane is called the **Map view** (middle) which displays the **World Topographic Map** is a basemap that serves as a reference map used as a background for your work. In the coming weeks, you will use different types of basemaps. The **World Hillshade** is an elevation map from the **living atlas** of ESRI. The third pane is the **Catalog pane** (right), which displays the contents of a project or portal or commands and settings related to an area of functionality, such as the Symbology and Geoprocessing panes (you will work with all of these in the coming weeks).

## 3. Explore the Navigate Group in the Map Tab

When you work with maps and scenes, you can zoom in and out and move around in the case of scenes, move up, down, and look around.

In the **Map** tab on the ribbon, in the **Navigate** group, there are various icons.

The **Explore** , **Full Extent** , **Fixed Zoom In** , **Fixed Zoom Out** , **Previous Extent** , **Bookmarks** , and **Go To XY** tool.

The default tool for maps and scenes is the **Explore** tool , which is used to move, pan, identify feature attributes via a pop-up, and zoom in and out of maps and scenes.

When you pan through a map or scene with the mouse, the pointer becomes a hand. Right-click and hold the mouse button and move the mouse up or down to zoom. The pointer becomes a magnifying glass when you click the right mouse button.

Some Explore tool capabilities are described in the image below.

- **Zoom In/Out** : scroll the mouse wheel to zoom in to or out from the cursor position

3

_EART29102 Practical 1_

- **Zoom In** : click **Shift** on the keyboard and draw a rectangle on the map where you want to **Zoom In** . To go to the previous extent right-click the mouse and point to “ **Previous Extent** ”

- **Pan** : click at any location on the map and then drag the map to pan

## 4. Map scale and coordinates

The scale of the current display in the data view is shown in the combo box below the map. Combo boxes in ArcGIS Pro allow you to select an option from a drop-down list. Therefore, you can use this combo box to specify a scale for displaying the data. The coordinates of the current position of the cursor are updated and displayed at the bottom of the window.

<!-- Start of picture text -->
Scale  Coordinates<br><!-- End of picture text -->

## 5. Adding and removing spatial datasets

There are two main ways to add spatial datasets. One way is to use the **Add Data** tool on the **Map** toolbar. Using the drop-down arrow on the **Add Data** button select **Add Data to map** and navigate to **Portal > My Organisation** and search for **Prac_1_data.gdb** then click **OK** .

Another way to add spatial datasets is from **ArcCatalog** . The ArcCatalog window displays the contents of folders and subfolders where spatial data are stored in the form of a catalogue tree. You can navigate through the catalogue tree to the desired dataset, and then drag the dataset and drop it into the data frame listed in the table of contents.

From Catalog select the **Portal** tab and **My Organization,** in the search box type **elevlidar** and rightclick **Add To Current Map** (it may take a while to load):

4

_EART29102 Practical 1_

Once a dataset is added, it is placed at the top of the layer list under the data frame in the table of contents. It also has the box to its left checked. If you uncheck the box, the layer will become invisible in the data view.

The drawing order of layers can be changed by selecting and dragging layers up and down in the **Contents Pane**

To **remove** a data layer, right-click on the name of the layer in the table of contents. A context menu (also called a contextual, shortcut or pop-up menu) pops up. It is a floating menu that appears at the location of the pointer when you right-click. From the pop-up menu, select **Remove.** The layer is then removed from the table of contents and the data view.

## 6. Vector data

With the **elevlidar** layer unchecked in the Contents Pane, the Map View shows a map centerd on Newton Creek in Superior, Wisconsin consisting of four layers: **SamplingSite** , **NewtonCreek** , **MurphyOil** , and **HogIsland** .

5

_EART29102 Practical 1_

These layers are different types of **vector** data comprising **shapefiles** . These layers can be classified and symbolized by different symbols. The map shows that Newton Creek starts from Murphy Oil Inc. and discharges into Hog Island. Five sampling sites were used as sampling locations to monitor the quality of the water creek.

Right-click the **Sampling Site** layer and select **Attribute Table**

A new pane opens below the **Map View** showing a table of **attributes** for that layer. The rows are known as **Records** and columns as **Fields** . Each **Record** represents information that is unique to a particular location. The **Fields** define the information in the attribute table and, in this example, each record includes:

- FID: a unique identifier for that record

- The type of vector data (point)

- The name of the site (1,2,3…)

- The location (latitude and longitude)

- • Some measurement data recorded for water samples at each site EC = electrical conductivity; pH, T = temperature and DO = dissolved organic carbon.

6

_EART29102 Practical 1_

Note that you can obtain the same information by clicking on any shape feature on the map, in the example below I clicked on site 2 and the pop-up box shows the information in the attribute table.

**Challenge 1:** Select the attribute tables for the NewtonCreek and MurphyOil layers, what kind of shape data is stored in each of these?

**Challenge 2:** The sample sites along Newton Creek can be labelled – see if you can work out how to add the labels to do this on your map.

## 7. Raster data

Add the raster data file called **elevlidar** to your map. A new data layer is added with elevation data.

7

_EART29102 Practical 1_

In the Contents pane, right-click “ **elevlidar** ”, select **Properties** , and then **Source** tab.

The Source tab includes six sections that provide detailed information about the “ **elevlidar** ” raster.

- **Data Source** : Show the location of the **“elevlidar”** raster

- **Raster Information** : This shows that the **“elevlidar”** raster has 9989 columns and 5105 rows. The raster consists of 1 band, and the cell size (resolution) is 6.289 × 6.289 feet. It also indicates that the pixel type is a floating point, meaning that the attribute table cannot be opened. The pixel depth of the raster is 32 Bit.

8

_EART29102 Practical 1_

- **Band Metadata** : shows the information about the raster.

- **Statistics** : shows the minimum, maximum, mean, and std. deviation of the raster elevation.

- **Extent** : this shows the coordinate extent in feet.

- **Spatial Reference** : shows that the coordinate of the **“elevlidar”** raster is registered in Customized Transverse Mercator and the datum is **D custom** . It also provides information about the parameters of the projection, such as false easting and false northing.

9

_EART29102 Practical 1_

Click OK after exploring the layer properties of the “ **elevlidar** ” raster.

## 8. Change the Name of the Map

In the Contents Pane, right-click the “ **Map** ”, select **Propertie** s, change the name to Superior, click OK

## 9. Save the Project

It is a good practice to save your changes periodically while you work. You can save the changes to your project or the project using different methods as follows:

Click the Save button on the **Quick Access toolbar** at the top of the app.

Click the Project tab on the ribbon and click Save.

Press Ctrl + S.

Save your project.

## 10. Improving the look of the raster layer

Although the raster layer contains elevation data, it is hard to visualise the relief. This can be improved by geoprocessing the data to obtain a **hillshade** layer.

10

_EART29102 Practical 1_

Click **Analysis** > **Tools** this opens the Geoprocessing pane and type **hillshade** in the search box. Select **Hillshade (3D Analyst Tools)** . When the **Hillshade** dialog box opens in the Geoprocessing pane then drag and drop the **elevlidar** layer from the **Contents** pane into the **Input raster** box. Accept all other defaults (including the output raster name) and click **Run** .

The **Hillshade** function produces a grayscale 3D representation of the terrain surface, with the sun's relative position taken into account for shading the image. Hillshading is a technique for visualizing terrain determined by a light source and the slope and aspect of the elevation surface.

11

_EART29102 Practical 1_

11. Convert the raster layer to contour lines (vectorisation) The Contour tool is another useful geoprocessing function to generate contour lines at a specified intervals.

**Challenge 3:** Search the Toolbox to find the **contour** function and generate layer containing contour lines at 10ft intervals.

**Challenge 4:** Label your contours with their heights.

Your project should look like the one below:

## 12. Set Map Extent

The map extent is defined by a set of coordinates that outline the area of the map or scene in the project. By default, the extent is the spatial extent covered by all features in all layers in the map or scene. This is a dynamic extent. It updates accordingly when data are added or removed from the map or scene. GIS users can set a custom map extent

On the **Map** tab in the **Navigate** group, click **Full Extent** button

The map will zoom to the whole world.

12

_EART29102 Practical 1_

Set the Extent to Custom Extent

Now set the **Extent** to a custom extent

Select the SamplingSite layer and right-click then Zoom to layer

Now zoom and move your map to make looks similar to the view and scale as shown below

13

_EART29102 Practical 1_

In Contents Pane, right-click the **Superior** map and click **Properties** to open the Map Properties dialog box. On the **Extent** tab, click **Use a custom extent** . Choose **Current visible extent** below the **Get extent from** to generate extent coordinates. Click OK to close the Map Properties dialog

box. Click the **Full Extent** button again. The Superior map will zoom to the **custom extent.**

Save your **Project.**

## 13. Further help

For further help with ArcGIS Pro basics watch the following ESRI training video:

**<u>htps://www.esri.com/training/catalog/5d816c0255cf937306d2d3ef/arcgis-online-basics/</u>**

14
