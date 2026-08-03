---
title: "Practical 6 -Remote Sensing"
source: "Sophomore/Hilary Term/EART29102/Practical/Week 6/Practical 6 -Remote Sensing.pdf"
type: pdf
---

_EART29102 Practical 6_

# Practical 6: Remote Sensing

### Learning outcomes

By the end of this practical you will be able to:

- Use ArcGIS online to easily visualize changes in land use.

- Be able to work with Landsat and Sentinel 2 imagary in ArGIS Pro.

- Understand how spectral enhancements are used in vegetation and mineral studies.

## Contents

|1<br>Introducton .................................................................................................................................... 2|
|---|
|2<br>Multdimensional Landsat Imagery ................................................................................................. 2|
|3<br>Retrieve historical imagery.............................................................................................................. 2|
|3.1<br>Locate the study area .............................................................................................................. 2|
|3.2<br>Add multspectral Landsat data .............................................................................................. 3|
|3.3<br>What can you see on the image? ............................................................................................ 4|
|3.4<br>Save the map ........................................................................................................................... 5|
|4<br>Show imagery over tme ................................................................................................................. 6|
|4.1<br>Enable tme animaton ............................................................................................................ 6|
|4.2<br>Confgure the tme animaton tool .......................................................................................... 8|
|4.3<br>Filter the highest-quality images ............................................................................................. 9|
|4.4<br>Measure the main pit dimensions ........................................................................................ 11|
|5<br>Moving to ArcGIS Pro .................................................................................................................... 12|
|5.1<br>Adding the Landsat imagery ................................................................................................. 12|
|5.2<br>Explore spectral informaton ................................................................................................. 14|
|6<br>Sentnel-2 imagery ........................................................................................................................ 17|
|7<br>Resources ...................................................................................................................................... 17|

This tutorial was originally developed by ESRI training Spatial Analysis with ArcGIS Pro

1

_EART29102 Practical 6_

## 1 Introduction

Landsat satellite imagery has become a living photo album of the Earth's surface since the NASA launched its first rocket on July 23, 1972. Landsat has since collected millions of images as new rockets were launched and camera technology improved. In this practical you will use selected Landasat images to see how an area of mining has changed over time, and learn how to analyse reflectance spectra to

The Chuquicamata mine in northern Chile is the largest open pit copper mine by excavated volume on the planet. It opened in 1882, is still operational today, and has expanded significantly over the last decades. In 2019, underground mining began at Chuquicamata as part of a multi-billion-dollar overhaul of operations. The effort aims to reach additional deposits amid slowing productivity and is expected to extend the useful life of the site by at least 40 years.  In this practical, you will use Landsat imagery to monitor the expansion of the Chuquicamata mining area and analyze the impact on the surrounding environment.

## 2 Multidimensional Landsat Imagery

Multidimensional raster data, or image cubes, consists of rasters or imagery that have been collected over multiple times, depths, or heights and are stacked into a single dataset. These data can be used to monitor changes and trends in environmental phenomena, urban development, natural resources, and more.

In this practical we will use ArcGIS online to analyses the imagery and then use more advanced processing of raster layers in ArcGIS pro.

## 3 Retrieve historical imagery

Landsat satellite imagery are available in ArcGIS Living Atlas of the World. The massive archive of Landsat images has been compressed into one data layer that can be viewed on ArcGIS Online.

#### 3.1 Locate the study area

You'll locate the Chuquicamata mine on a map in ArcGIS Online.

Sign in to your ArcGIS online UoM account.

On the ribbon, click **Map** .

In the **search box** to the upper right of the map, type **Chuquicamata mine** and press **Enter.**

2

_EART29102 Practical 6_

Close the pop-up.

In the map, use the **zoom tools** and click the **Zoom Out** button **one** time to display the whole of the mine site.

The map displays the whole of the mine works.

#### 3.2 Add multispectral Landsat data

The next steps are to change the basemap so that labels show and add satellite imagery from the ArcGIS Living Atlas.

On the left column, click **More** or **…** , then select **Basemap** and choose **Light Grey Canvas.**

3

_EART29102 Practical 6_

On the right again, click on **Layers** and select **Living Atlas** from the

In the search box, search for **Multispectral** and press **Enter** .

Among the search results is the Multispectral Landsat layer. Add the Multispectral Landsat layer to the map.

You can see both the imagery and the basemap labels, which help provide context and orientation.

By default, there is a filter that limits the imagery displayed in the Multispectral Landsat layer to very recent captures. You'll remove that default filter to have access to all available imagery since the 1970’s.

On the right side, open the **Filter window.**

And press **Clear all** to remove the filter.

#### 3.3 What can you see on the image?

The following features should be visible on the image.

- The mining town of Chiquicamata – abandoned in 2007 because of the close proximity to the main pit.

- Terrace-like mining benches in the pit, which support work equipment and catch material from debris slides, appear as concentric rings in the pits.

- Piles of waste rock containing low concentrations of minable metals lie adjacent to them.

- Tailings ponds holding residual material from the ore enrichment process.

4

_EART29102 Practical 6_

#### 3.4 Save the map

Save your map and give it metadata.

On the right, click **Save and open** , then **Save as** .

For the **title** , type _Change in Chuquicamata mine, Chile_ .

For the **tags** , type the following words and press **Enter** after each one:

Chile

Historical

5

_EART29102 Practical 6_

Imagery

For the **summary** , type _This map is a collection of images showing four decades of change in the Chuquicamata mine, Chile_ . Click **Save.**

You've created a map that will serve as a foundation for your presentation on changes in the Chuquicamata mine, Chile. Next, you'll delve into the historical collection of the Multispectral Landsat layer and create a time animation to show certain images in chronological order.

## 4 Show imagery over time

The imagery layer that you added to the map contains all the images captured by the Landsat satellites since the program began. As such, the layer can be time-enabled and filtered to select out and display only the images you need for your animation.

#### 4.1 Enable time animation

First, enable the time function for the layer. Enabling time on the layer allows you to search through 40 years of satellite imagery for your study area.

6

_EART29102 Practical 6_

In the **Contents pane** , point to the **Multispectral Landsat** layer and toggle **Enable time** .

The time animation toolbar appears at the bottom of the map window. The map also changes to show only imagery within the first date range on the timeline: July 24, 1972, to July 24, 1977. Your map viewer turns a colour, such as white or blue, because of an error in capturing the first image of this area.

The Landsat program began in 1972, and early Landsat imagery can often be of poor quality. Later, you'll filter this and other problematic images out of the dataset so only high-quality images are shown. First, you'll look at all of the images to see which ones might be useful for your presentation.

On the **time animation** toolbar, click the **Play/Pause** button.

The timeline plays, cycling through all available images in chronological order.

You can see the differences in the images over time. The speed at which the animation progresses is not ideal for observing changes, so you'll change the default settings of the time animation tool to lower the playback speed.

7

_EART29102 Practical 6_

Some images may not load before the timeline continues to the next image. You may need to play the animation more than once to see all of the images.

When you are finished watching the time animation, click the Play/Pause button again to pause the animation.

#### 4.2 Configure the time animation tool

Change the default settings in the time animation toolbar to play the animation at an appropriate speed, and to display images by decades to start building your presentation.

On the **time animation** toolbar, click the **Configure** button.

In the **Play rate** window, adjust the playback speed to the slowest setting and close the window.

Play the time slider again. While the time animation plays more slowly, sometimes the imagery changes even when the time slider does not. The time slider is currently divided into five-year intervals, and it's possible for more than one image to have been taken during these intervals. You'll lower the display interval to show only one image per tick of the timeline. Doing so will cause the time animation to take a long time to span the entire chronology of Landsat imagery, so you'll also narrow the time encompassed by the timeline to show only imagery between 1972 and 1980. Later, you can look at imagery from the other decades. This way, you can look at the imagery in more manageable 10-year time periods and also choose the best image from each decade to include in your presentation.

**Pause** the animation.

Click the **Configure** button. In the **Start and end points** window you have the option of customising the time span and display intervals of the animation.

Change **Start time** to 7/25/1972 12:00 AM, and **End time** to 1/1/1980 12:00 AM

Then in the **Time intervals** window, select **Length of one interval** and change it to 1 year.

Close the options and play the time animation again.

8

_EART29102 Practical 6_

Most of the years between 1972 and 1980 have no imagery. In 1973 and 1975, however, the Landsat program captured a usable image of the area.

You'll use this image in your presentation to show land use in 1975. Later, you'll filter the Landsat dataset to include only this layer, as well as a few others. To do that, you'll need to know the layer's acquisition date, or the date the image was captured by the satellite.

Click the image in the map window to open a pop-up for the image.

The acquisition date for this image was February 15 1975. You'll use this date in the next section when you filter the dataset.

The Landsat program did not capture an image for the area during the 1980s. In your presentation, this decade will appear blank.

After reviewing animations for each time period, we have images for the following dates that representative for each decade:

##### **Decade Date**

1970s 2/15/1975 1980s No image 1990s 4/4/1990 2000s 10/22/2005 2010s 11/29/2013 2020s 1/28/2024

The Landsat images are displayed by default as a natural colour composite, where the red, green, and blue bands are displayed with the corresponding channels, so features in the image are rendered as the human eye would see them in real life.

#### 4.3 Filter the highest-quality images

Now you will filter the Multispectral Landsat layer to display only the best image from each decade.

On the right, open the **Filter** page, ensuring that you have **Multispectral Landsat** selected.

9

_EART29102 Practical 6_

This window allows you to set a filter on the data to only display parts of that data. You can build filters based on attribute values. You'll build a filter based on the Acquisition Date attribute for the different decades.

Click **Add new** five times, giving you five new filters to work with.

From the drop-down menu at the top, pick **Any of the following are true** .

For each of the filter expressions, choose **Acquisition Date** as the field, choosing **is between** as the first option. This will allow you to input two timestamps, these will be the start and end of the day on which each image was acquired.

10

_EART29102 Practical 6_

Repeat this for each image date: 15/2/1975, 4/4/1990, 22/10/2005, 29/11/2013 and 28/01/2024. Note you may have to set the **End date** first, as the option will not allow a **Start date** after the **End date.**

Click **Save.**

The filter is applied, but the images may not be shown because the time animation toolbar is still configured to only show images from a small range of dates.

On the animation toolbar, click the **Configure** button and edit the **Start date** and **End date** values to be 01/01/1970 and the most recent date of your imagery, respectively. Then, in the **Time intervals** tab set the time interval to be 10 years. Close the **Configuration** window.

Click the **Play/Pause** button to view the images.

You may need to cycle a few times for all the images to be displayed with the **slowest** time setting.

Only the images for the five dates you chose when you created the filter appear. No image appears between 1980 and 1990, because there were no images for this decade.

#### 4.4 Measure the main pit dimensions

The measurement tools can be used to determine the change in dimension of the main pit. Use the time animation tool to find the image for the 1990’s

On the right hand panel, open the **Map Tools** and click on **Measurement** . **Click** the southern-most point of the main pit. **Double-click** the northern-most point to obtain a measurement.

In 1990, the main mine pit was approximately 3.5 km long.

Change to the most recent image in 2020’s and measure the length of the mine again.

11

_EART29102 Practical 6_

The main mine pit is now 4 km long. Notice also that several secondary pits have appeared or expanded between 1990 and 2024.

##### **Close** the **Measure Distance** tool.

## 5 Moving to ArcGIS Pro

- 5.1 Adding the Landsat imagery

Open a new project in ArcGIS Pro and from the **Catalog** pane select **Portal** > **Living Atlas** and type **multispectral** in the search box.

When multispectral landsat appear in the list **select** and **drag** it to the **Contents** pane. If this does not work, **Right click** and select **Add to Current Map.**

Search for **Chuquicamata copper mine** and a natural colour image should appear.

With the **Multispectral Landsat** layer selected, on the ribbon click **Data** and note the different **Processing Templates** available with a short description of each available

12

_EART29102 Practical 6_

We are going to save the imagery to a local disk for further processing.

With the mine in view as the image below:

Change the **Processing Template** to **Natural Colour with DRA**

13

_EART29102 Practical 6_

**Right click** the **Multispectral Landsat** layer and the click **Data** > **Export Raster**

In the **Export Raster** pane name your output raster _Chuquicamata_Landsat_ then set **Clipping Geometry** to **Current Display Extent** and **Pixel Type** to **16 bit unsigned** (this is default for Landsat imagery).

Now click **Export.**

A part of the Landsat image service is stored locally and appears as a new layer in the contents pane.

#### 5.2 Explore spectral information

Mineral deposits commonly show a spatial association with hydrothermal alteration of the surrounding rocks which has proved useful in the exploration of mineral deposits. Hydrothermal alteration is frequently identified by the presence of iron-oxides and hydroxyl-bearing minerals (clays). These minerals have diagnostic spectral features in the infrared region of the electromagnetic spectrum that allow their remote identification.

A single Landsat TM image is made of several files, which include several surface reflectance spectral bands. The bands correspond to the following portions of the electromagnetic spectrum, as described in Landsat 8 Operatonal Land Imager.

14

_EART29102 Practical 6_

There are nine spectral bands, (wavelengths) with spatial resolutions as follows:

Band 1 Coastal Aerosol (0.43 - 0.45 µm) 30 m

Band 2 Blue (0.450 - 0.51 µm) 30 m

Band 3 Green (0.53 - 0.59 µm) 30 m

Band 4 Red (0.64 - 0.67 µm) 30 m

Band 5 Near-Infrared (0.85 - 0.88 µm) 30 m

Band 6 SWIR 1(1.57 - 1.65 µm) 30 m

Band 7 SWIR 2 (2.11 - 2.29 µm) 30 m

Band 8 Panchromatic (PAN) (0.50 - 0.68 µm) 15 m

Band 9 Cirrus (1.36 - 1.38 µm) 30 m

Band ratioing is a technique which divides the digital numbers i.e. the brightness values, corresponding to the peaks of high and low reflectance curve of one band by that of another band. The Iron Oxide ratio has been used to identify hydrothermal alteration minerals associated with copper mineralization. The Iron Oxide band ratio uses spectral reflectance information from the red and blue portions of the electromagnetic spectrum because iron oxides or hydroxides have high reflectance at 0.63-0.69μm (Red band) and high absorption at 0.45-0.52μm (Blue band).

The following band ratios are commonly used:

4/2 (iron-oxides)

6/7 (hydroxyl and clay minerals)

6/5 (ferrous minerals)

On the **ribbon** , click the **Imagery** tab then click the **Indices** and in the **Geology** group click the **Iron Oxide** button.

15

_EART29102 Practical 6_

A new multidimensional layer is added to the map.

16

_EART29102 Practical 6_

Bright areas are places of higher iron oxide – notice how these correspond to the brown/reddish areas on the natural colour image. Notice also that the pit and wastes are relatively dark indicating lower iron oxide.

Now add a **Clay Minerals** index  – where are they most concentrated?

**Save** the project.

## 6 Sentinel-2 imagery

In the Catalogue pane > Portal then connect to Living Atlas and search for Sentinal-2 views.

The better spatial resolution of the Sentinel 2 imagery (10 m pixel resolution) versus the Landsat 8 image (30 m) is immediately apparent.

Use the iron oxide index – you will be prompted for the bands. Recall that iron oxides have high reflectance at 0.63-0.69μm (Red band) and high absorption at 0.45-0.52μm (Blue band). Use the information below to select the appropriate bands.

## 7 Resources

USGS Earth Shot – Chuquicamata Mine, Chile

<u>htps://eros.usgs.gov/earthshots/chuquicamata-mine-chile</u>

17
