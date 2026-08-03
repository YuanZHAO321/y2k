---
title: "Lecture - 3D geospatial techniques"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 9/Lecture - 3D geospatial techniques.pptx"
type: slides
---

## Slide 1

### 3D geospatial techniques

- Rufus Brunt

## Slide 2

### Intended Learning of lecture and practical

- Ability to explain what ‘3D’ is in the digital world

- Recap geographical datums and discuss implications for the 3rd dimension

- Exploration of GIS data definitions: continuous/ discrete/ raster/ vector

- Application of 2D geostatistical techniques within the 3rd dimension

## Slide 3

### 2D vs. 3D

- We tend to work on a paper map or flat screen Both are 2D surfaces - So - what is 3D?

- Wolfenstein 3D (1991)

- One of the first commercial “3D” games

- But how 3D is it?

- Raycasting: this is a 2D rendering technique to give sprites/ walls the appearance of 3D.

- However – the game plays in x, y space. There is no access to the 3rd dimension

- Sometimes referred to as 2.5D

- I.D. games

## Slide 4

### What is meant by 3D?

- 2D geological map of the Isle of Mull

- With x and y coordinates you could find any point on this map

## Slide 5

### What is meant by 3D?

- Digital terrain model (DTM) of the Isle of Mull

- The map is a surface existing in 3D space. But a point on this surface can still be described using only x and y coordinates.

- This is not 3D  (mathematically speaking a ‘surface’ is always 2D)

## Slide 6

### True 3D

- Volume is integral in geospatial 3D

- To specify a location within these datasets we need to specify x, y and z coordinates.

## Slide 7

### Where do we measure from?

- In the lat – long framework:

- X is defined by the prime meridian, Greenwich

- Y is defined by the equator – the plane equidistant between the Earth’s geographical poles

- Z – how do we define height?

- Image taken from the Royal museums Greenwich website: https://www.rmg.co.uk

## Slide 8

### The problematic Z dimension

- Earth is not spherical….

- Modern measuring methods prove Earth is an oblate spheroid:

- The equatorial diameter is 12,700 km

- The polar diameter is about 40 km shorter

- Outcome:  distance from the centre of the Earth is not a valid Z

## Slide 9

### Vertical datumsGeodesy: the science of measuring Earth’s shape, orientation and gravity field

- Ellipsoid:  an idealised mathematical model of the Earth.

- National map grids typically use an ellipsoid closely approximating the local geoid.  This work at ‘local’ scale, but is too general for global maps.

- Affected by:

- lithological density

- Tides

- Plate tectonics

- Water depth

- Transient crustal heating

- etc

- red = gravity high e.g. Europe excess mass due to dense crust and deep Moho;

- blue = gravity low e.g. Sea level is 106m below MSL over the Indian Ocean Geoid low.  Caused by hot, low-density mantle plumes (Pal & Ghosh, 2023): https://doi.org/10.1029/2022GL102694

- Reference ellipsoid

## Slide 10

### Z measurements

- UK ordnance survey

- Uses the OSGB36 coordinate reference system: tied to mean sea-level at Newlyn, Cornwall.  This is a traditional datum – a triangulation network of trig pillars fitted to the Airy 1830 ellipsoid.

- Ordnance Survey GPS permanent network

- The more modern OS GPS is tied to GB ETRS89 (European Terrestrial Reference System 1989) – a version of WGS84 (World Geodetic System 1984).

- GPS

- In contrast GPS uses the global WGS84 coordinate reference system.  This is tied to the global GRS80 ellipsoid (Geodetic Reference System 1980).

- Translations

- All these systems will produce different z values – and maybe changes in xy.  A mathematical transform is needed to convert between coordinate frameworks.

- Orthometric height

- Topographic surface

- Ellipsoid height

- Ocean

- Geoid height

- Mam Tor trig pillar  (Creative commons)

- Geoid height

## Slide 11

### Digital space

- VOXELS

- Esri

- A 3 dimensional pixel used to display 3D images.

- Each voxel has an x, y, z position and a set of descriptors used to describe volume – or other data such as discrete class, time, density, porosity, etc

- The smallest unit of information in a 2D raster image.  In GIS a pixel is a cell in a regular array of data values. Each pixel has an x,y location and set of descriptors such as  R,G,B, or height.

## Slide 12

### Creating a 3D model

- Voxel layers can be created using discrete data or continuous data

- Esri:  ArcGIS Pro documentation

- Esri:  ArcGIS Pro documentation

- Dutch soil profiles. Voxels are coded using discrete data that represents soil categories.

- Gulf of Mexico temperature distribution.  The plot is a geostatistical interpolation of continuous data recorded at many individual sample points.

## Slide 13

### Discrete data

- Information assigned to defined values, usually integers.

- Can have different functions, but must have defined boundaries.

- Counted variable - examples:

- Pets per household

- Town population

- Or used to classify:

- Land use

- Geological map unit

- Road type

| class | Road type | Symbol |
| --- | --- | --- |
| 1 | Path |  |
| 2 | Track |  |
| 3 | B road |  |
| 4 | A road |  |

## Slide 14

### Continuous data

- A measured variable that could have any numeric value.

- There are no boundaries: values vary continuously.

- 2D GIS examples:

- Elevation

- Rainfall

- Satellite photos

- Gravity

## Slide 15

### Creating a 3D volume using 3D kriging in Arc Pro

- A geostatistical interpolation tool that uses Empirical Bayesian Kriging methodology to interpolate points in 3D

- Kriging: spatial interpolation between point data

- Bayesian: employment of prior knowledge into a calculation

- Here, prior knowledge is an estimation of the semi-variogram and associated uncertainty.  ArcGIS iterates, each time estimating a new semi-variogram to close in on the final model.

- The tool generates a series of 2D horizontal slices which can be scrolled through

- The Geostatistical layers can be combined to create a 3D voxel layer

## Slide 16

### 3D visualisation of volumetric data

- Volumetric realisations provide a powerful method of visualising 3D data. E.g.

- Subsurface data (e.g. porosity, metal concentration)

- Atmospheric data

- Oceanic data (e.g. temperature, pollutant concentration)

- Here – discrete data categories are visualised individually

- Esri animation of daily relative humidity with altitude in 2003:  ArcGIS Blog

## Slide 17

### 3D visualisations: slices

- Oceanic nitrate concentration data

- Volumetric data is sliced as:

- 2D vertical slices

- Isosurface (a surface created from equal concentration values)

- We will be slicing this afternoon

- Esri:  ArcGIS Pro documentation

## Slide 18

### Introduction to linked practical

- © Natural Resources Wales

## Slide 19

### Critical minerals/ metals: projected demand

- The expected global demand for critical metals in a net zero world

- This can be a dirty business

- Other uses

- Electricity networks

- Grid storage batteries

- Electric vehicles

- Wind

- Solar PV

- Other low-energy power generation

- Data compiled by the IEA (International Energy Association) https://www.iea.org/topics/critical-minerals

## Slide 20

### Cobalt – critical for Li-ion battery stability

- “Blood cobalt” comes from DRC

- Apple, Tesla, Samsung and Microsoft all implicated in cobalt supply chain that extracts minerals using slavery and child labour

- Toxicology linked to heart, thyroid, liver, and kidney problems

## Slide 21

### Nickle – cathode in Li-ion batteries

- Rain forest destroyed in Sulawesi and Maluku to access Nickle.

- Some large scale mining operations are illegal. Large consequences for environment particularly through poor control of waste products and drainage.

- Toxicology:  causes cardiovascular and kidney diseases, lung fibrosis, lung and nasal cancer. May disturb the human genome.

- Is it better for critical mineral extraction to take place in countries with robust environmental policy and government accountability?

- © Ian Morse for The Washington Post

## Slide 22

### Copper (Cu): critical for all electrical technology

- An electric car requires 6x more mineral input than a car running on hydroarbons (IEA, 2024).

- MW for MW, an offshore windfarm requires 13x more mineral resource than a gas power station (IEA, 2024).

- Should the UK aim for Cu self-sufficiency?

- Alderley Edge: Malachite and azurite in the Engine vein.

- Photo copyright: Mike Peel, creative commons

## Slide 23

### Coed-y-Brenin

## Slide 24

### What is a porphyry deposit?

- sdsd

- Both figures from:  Park et al, 2021

- https://doi.org/10.1038/s43017-021-00182-8

- Associated with convergent plate tectonics

- Downgoing slab sources O2 rich waters and hydrous melts

- Mantle wedge:  partial melting in oxidising conditions deplete sulphides.  Cu and Au have an affinity for sulphides and are preferentially incorporated into ascending sulphide rich melts

- Hydrous basaltic magmas ascend to mantle-crust boundary (30-70km) where magma evolves through fractionation / magmatic differentiation concentrating ore-forming fluids

- Rising evolved magmas become fluid saturated as overburden pressure drops

## Slide 25

### What is a porphyry deposit?

- Relative low-density fluids liberated from shallow magmatic intrusions (1-7km) accumulate at top of intrusion.

- The high pressure fluids hydraulic fracture (frack) the top of intrusion and country rock.

- The fluids condense and cool to a metal rich brine

- Metal sulphides precipitated from cooling brines forming halos around the intrusions

- Richards & Mumin, 2013:  https://doi.org/10.1130/G34275.1

## Slide 26

### What is a porphyry deposit?

- Explosion breccia pipe:

- Bleached / shattered Hydrous silica. Sometimes ‘pods’ of copper

- Sericitic zone: hydrothermally decomposed microtonalite – here, iron stained – pyrite rich

- Microtonalite:

- un-altered

- Richards & Mumin, 2013:  https://doi.org/10.1130/G34275.1

- hydrothermally decomposed microtonalite – here, enriched with copper :

## Slide 27

### Porphyry enrichment

- Porphyry halos are large, low grade bodies:  a good one is 1% Cu

- Supergene enrichment is a redox process taking place near the surface.  It can enrich deposits to >2%

- O2 rich meteoric waters weather and leach metals from the porphyry, and re-deposit in deeper, reducing conditions.

- Reko Diq Mine, Pakistan. Electromagnetic survey and interpreted crustal section through enriched supergene (Witherly, 2003: https://doi.org/10.1080/14432471.2023.2287269).

- Reko Diq has 5.9 billion tonnes of ore @ 0.41% copper and 0.22ppm gold (0.000022%)

## Slide 28

### Back to Coed-y-Brenin

- Capel Hermon

- Greenish oxidised chalcopyrite, disseminated and in fractures

## Slide 29

### Mining history 1850’s to 1915

- Gasdir mine

- approx. 1925

- Shallow mines produced

- 13,077 t Cu ore

- 8275 oz Ag

- 735 oz Au

- Eventually closed due to affects of mine tailings polluting fisheries

- © mindat.org

## Slide 30

### Dolfrwnog Mine and ‘turf’ mine

- Very localised supergene enrichment

- A redox process:  Oxygen rich ground waters percolating through the porphyry reached the surface in a peat bog.  Strongly reducing conditions in the peat led to precipitation as native copper and gold.

- Peat dug and smelted as ore between 1824 and 1865.

- Sea Pinks (Armeria maritima) tolerant of metals, including copper

- Probably looked something like this  (from Minedat.org)

## Slide 31

### Coed-y-Brenin data

- Series of exploration wells drilled in the 1970s

- Well data has been input to an Excel spreadsheet

- Describes Cu content as well as other metals

## Slide 32

### Would you dig up Eryri (Snowdonia) to access it?
