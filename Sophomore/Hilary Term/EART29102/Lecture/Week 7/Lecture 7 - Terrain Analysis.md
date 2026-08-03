---
title: "Lecture 7 - Terrain Analysis"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 7/Lecture 7 - Terrain Analysis.pdf"
type: pdf
---

# Terrain Analysis

## Lecture content

- ➢ What is terrain analysis?

- ➢ Data sources, types and formats.

➢ Slope, aspect, curvature and topographic profiles. ➢ Catchment and hydrology.

➢ Line of sight and viewsheds.

- ➢ Solar radiation mapping.

# What is Terrain Analysis

- Complexity: spheroid < geoid < land surface (terrain).

- Using topographic data to derive terrain features.

   - the morphology of terrain surface.

   - the influence of terrain on environmental processes.

- Contours, spot heights, DEM (raster) and TIN (vector).

_different ways of representing the same continuous surface at the same scale and extent_

https://gistbok.ucgis.org/bok-topics/triangular-irregular-network-tin-models00

# Main digital terrain data sources

- Ground surveys.

- Photogrammetry.

- Radar altimetry.

- Interferometric synthetic aperture radar (InSAR).

- • Airborne laser scanning (LiDAR).

- Most of these are in the form of, or can be readily transformed to DEM.

# Applications of terrain analysis

Terrain analysis is about how the shape of the land influences or reflects natural processes, hazards, ecosystems, and human influences.

**Mapping drainage networks** — identifying channels, flow paths, and watershed boundaries for river management.

**Flood modelling** — locating floodplains, flow bottlenecks, and overtopping points. **Erosion risk assessment** —to predict where soil loss is likely.

**Wetland and groundwater recharge mapping — identifying depressions, low-** areas. **slope zones, and convergent flow**

**Geomorphological mapping** of ridges, valleys, terraces, and scarps, dunes. **Shape parameters** of volcanic landforms (e.g. subglacial edifies on Mars) **Detecting landslide-prone slopes.**

**Mapping glacial features** such as drumlins, moraines, and meltwater channels.

# Triangulated irregular networks

- ➢ TIN - using contiguous, nonoverlapping triangles linking 3 adjacent elevation points.

- ➢ Independent of data scale = flexible in level of detail.

- ➢ Efficient in terms of data storage.

➢ TIN less useful than DEM when surface is flat (e.g. plateau, deserts).

# TIN with hard and soft breaklines

_A breakline is a line feature with elevation values that forces the TIN surface to follow a specific shape. They prevent the interpolation from smoothing over important terrain edges._

- ➢ _Hard breakline_ – a discontinuity in slope of a surface.

-

- ➢ _Soft breakline_ does not change local slope of terrain surface.

   - ➢ Hard breaklines keep water inside channels; soft breaklines guides the flow along the deepest parts of channels.

   - ➢ Hard breaklines preserve scarps; soft breaklines maintain natural curvature.

# Primary terrain attributes

- ➢ Elevation, slope, aspect, plan and profile curvature are primary terrain attributes.

➢ Flow direction, flow accumulation, flow length, flow order, drainage network and catchment area are derived (hydrological) characteristics of a terrain surface.

- ➢ In GIS, they are mainly derived from DEM or TIN and represented in raster layers.

# Secondary terrain attributes

- ➢ Secondary attributes are computed from two or more primary attributes.

- ➢ Quantify the role played by topography in redistributing water in the landscape and in modifying the amount of solar radiation received at the surface.

- ➢ These attributes affect soil characteristics, distribution and abundance of soil water, susceptibility of landscapes to erosion by water, and the distribution and abundance of flora and fauna.

# Slope

Slope map

# Aspect map

# Terrain profile

# Surface curvature

- Amount by which a surface deviates from being flat.

- **Profile curvature** is the rate of change of slope in the direction of the maximum slope.

- **Plan curvature** is the curvature perpendicular to the direction of the maximum slope

Profile curvature = maximum slope of this surface

Planform curvature = convergence/divergence

https://www.esri.com/arcgis-blog/products/product/imagery/understanding-curvature-rasters/

# Profile curvature map

**Slope** influences the overall rate of movement downslope, **aspect** determines the direction of flow, **profile curvature** affects the flow acceleration and erosion/deposition rate, and **plan curvature** affects the convergence and divergence of flow.

# Watershed analysis

- ➢ Models the movement of water over the land surface.

- ➢ Track pollution sources to locate potentially affected streams e.g. agrochemicals, outlet pipes from factories.

- ➢ Estimate stream flow for ungauged

   - areas.

- ➢ Predict water quality.

- ➢ Analyse historic and future climate predictions.

- ➢ Understand sedimentation

processes.

- ➢ Characterise landforms.

# Hydrologically correct DEM

- Checking the DEM for sinks (hydrological conditioning).

- Areas which are pits, surrounded by higher elevation values.

- Whilst these can occur naturally, often they result from errors in the input DEM.

- Bridges, roads, quarries, sinkholes or misrepresentation of narrow-sided channels can all result in sinks.

# Hydrologically correct DEM

# Flow direction

_DEM – starting raster_

_flow accumulation – derived raster_

# Flow accumulation map

_High values = stream channels; zero values = ridgelines_

# Drainage network

Threshold values : 1000 cells

Threshold values : 7000 cells

➢ Threshold values are numerical cut-offs used to decide where surface runoff becomes a stream. Thresholds convert continuous flow accumulation into a discrete drainage network.

# Catchment boundary

A pour point in GIS is the specific point where water flows out of a catchment. It is the lowest point on a watershed boundary and the location where all upstream flow converges and “pours” into the next downstream area.

<!-- Start of picture text -->
Landslide risk criteria<br>Utcubamba River Basin, Peru<br>Rivera et al. (2025)<br>https://doi.org/10.3390/app15179423<br><!-- End of picture text -->

# Landslide risk zoning and mapping

_Rivera et al. (2025) https://doi.org/10.3390/app15179423_

# Visibility analysis: Line-of-sight

- **_Line of sight_** Draws a line between the observer point and the target point to indicate the visibility (visible or obstructed) along the line between the given points.

# Typical output of line-of-sight analysis

# Visibility analysis: Viewshed

Green = visible from blue point.

- **_Viewshed_** Shows the visibility (visible or obstructed) of an area from a specified viewpoint.

https://giscrack.com/viewshed-analysis-using-the-geodesic-viewshed-tool-in-arcgis-pro/

# Visibility analysis: Viewshed 2

https://pro.arcgis.com/en/pro-app/3.4/tool-reference/spatial-analyst/viewshed-2.htm

# Solar radiation mapping

- ➢ Estimate spatial and temporal distribution of solar radiation on the Earth’s surface.

- ➢ Solar radiation is radiant energy emitted by the Sun.

- ➢ **Direct radiation** propagates unimpeded in

   - a direct line from the Sun to the receiving surface.

- ➢ **Diffuse radiation** is scattered by clouds and dust.

- ➢ **_Reflected radiation_** is the direct and

   - diffuse radiation reflected by nearby terrain towards the location of interest.

- ➢ Total or **global** solar radiation is the sum of the direct, diffuse and reflected radiation.

https://desktop.arcgis.com/en/arcmap/latest/tools/spatial-analysttoolbox/modeling-solar-radiation.htm

# Hemispherical viewshed

➢ Upward–looking hemispherical viewshed model (DTM).

➢ Maximum angle of sky obstruction in all directions. ➢ Used in combination with sunmaps and skymaps. ➢ Calculate solar radiation for each location.

# Sunmap and skymap

Sumap used for direct radiation (39-deg N)

Skymap used for diffuse radiation

## Sunmap and skymap in a hemispherical viewshed

# Global solar radiation map

Surface solar radiation maps Rooftop solar power estimates

# Homework and Resources

- ➢ Read Chapter 8 of course textbook: Terrain Analysis.

➢ Take the quiz to test your basic understanding (on Canvas).

### **Further resources**

ESRI Training: Terrain Analysis Using ArcGIS Pro

https://www.esri.com/training/catalog/57630436851d31e02a43f18f/terra in-analysis-using-arcgis-pro/

Esri Storymap: Terrain Analysis Case study: Rauriser Ache Catchment https://storymaps.arcgis.com/stories/d21814c2303448ef84a6d50ae571c2 <u>4b</u>

## OCR 补充（原文中无文字层的页面）

_(以下内容由图片 OCR 识别得到，原文件该处无可提取文字。**识别质量低**——原件疑为手写或图件，文字大多不可靠，仅作线索，务必对照原件。)_

### Page 9

Slope

Rise (/)

<—— Run (¢) ——>

Percentslope: 6= 100 (h/d) (%)
Degree slope: @=arctan(h/d) (degree)

### Page 10

Slope map

### Page 11

Aspect map

SZ

NW

W270°

sw

[sem
GER Soctrrwees (2025-2475
BEE Wren rar sone 5)
= treat (292 5.337 5
BEE erm (297 5-280)

### Page 12

Terrain profile

Vertical exaggeration 3.0 X

1000 7400 1800

PaO
TR

Orstance

Elevation (m)
2700 - 3000
2400 - 2700
2100 - 2400
1800 - 2100
1400 - 1800

BS 100 «200

[) 800 - 1100
500 - 800
200 - 500

### Page 17

Hydrologically correct DEM

{d) DEM without sinks {e) Drainage lines from the DEM without sinks
