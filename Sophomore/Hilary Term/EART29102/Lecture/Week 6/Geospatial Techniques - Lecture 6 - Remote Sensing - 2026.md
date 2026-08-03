---
title: "Geospatial Techniques - Lecture 6 - Remote Sensing - 2026"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 6/Geospatial Techniques - Lecture 6 - Remote Sensing - 2026.pdf"
type: pdf
---

**EART29102 Geospatial Techniques**

_Lecture 6: Remote Sensing_

# Lecture content

- ➢Remote sensing data and applications.

- ➢Electromagnetic Spectrum Radiation and spectral reflectance.

➢Spectral, spatial and radiometric resolution.

- ➢Landsat and Sentinel satellites.

- ➢Image preprocessing, enhancement and transformation.

- ➢Radar and Lidar imaging.

# Remote sensing data

- Techniques for collecting environmental data from a distance without coming into direct contact with the objects of interest.

- Record the magnitude of electromagnetic energy flux that is reflected or emitted from the objects on the surface or within the atmosphere (normally imagery).

- Aeroplanes, satellites, and UAVs equipped with sensors.

<!-- Start of picture text -->
Lidar, Radar (and Sonar)<br>Landsat and Sentinel 2 satellites<br><!-- End of picture text -->

https://www.earthdata.nasa.gov/learn/backgrounders/remote-sensing

# Applications of remote sensing

- Urban monitoring and disaster management - floods, wildfires, dust storms, landslides, and earthquakes.

- **Climate change** trends - greenhouse gases and air pollution.

- Agriculture - crop health, yield estimation and precision farming.

- Forestry management - tracking deforestation and assessing biodiversity.

- Water resource management – monitoring the quality and quantity of lakes, rivers, wetland areas and oceans.

- Archaeological studies.

- Environmental conservation.

- Land use and infrastructure planning.

# Electromagnetic radiation (EMR)

##### **DEFINITION**

- Electromagnetic (EM) radiation is a form of energy capable of propagating

   - through a vacuum and interacting with matter.

- Can be described using two distinct concepts

      1. The energy is in the form of a continuous transverse **_wave_** , consisting of oscillating and orthogonal electric and magnetic fields

      2. The energy is in the form of discrete indivisible packets, or photons, which essentially behave as **_particles_**

- The wave concept describes how electromagnetic energy is propagated, refracted and reflected, whereas the particle concept describes the detection of electromagnetic energy by a sensor

# Electromagnetic radiation (EMR)

###### **PROPERTIES**

- All objects (> 0 K) emit electromagnetic radiation; transmitted, refracted and reflected.

- Can be characterized by three main properties

###### **_1. Wavelength_**

###### **_2. Frequency_**

###### **_3. Amplitude_**

<!-- Start of picture text -->
Velocity of EM energy,<br>𝑐= 𝑣𝜆<br>c  = the speed of light (~3 x10 8  ms -1 ),<br>v  = frequency,<br> = wavelength<br><!-- End of picture text -->

# Electromagnetic radiation (EMR)

##### **INTERACTIONS**

- Energy reaching a planetary body can interact with the matter present.

- Interaction can change characteristics of incoming radiation (e.g. intensity, direction, wavelength, polarization and phase) → remote sensing looks for these changes

Interactions:

**_1. Transmission_**

**_2. Absorption_**

_Volume phenomena_

**_3. Emission_**

**_4. Scattering_**

**_Surface phenomena_**

**_5. Reflection_**

# Electromagnetic radiation (EMR)

##### **WAVELENGTH**

- Amount and wavelength of energy depends on temperature of object.

- Higher T = more energy, shorter (peak) wavelength.

_Black body emittance spectra at different temperatures, as a function of wavelength._

# Electromagnetic radiation (EMR)

##### **WAVELENGTH**

- No object is perfect black body.

- **_Emissivity_** = ratio of emittance of a body and that of a blackbody.

# Electromagnetic Spectrum

- Convenient to divide the electromagnetic spectrum into different regions

- Arbitrary in reality; no sharp breaks.

# Electromagnetic Spectrum

|**Region**|**Wavelength**||
|---|---|---|
|**Gamma-ray**|< 0.03 nm|Complete absorption by upper atmosphere. Cosmic-ray excitation and emission.<br>_Passive_|
|**X-ray**|0.03 to 30 nm|Complete absorption by upper atmosphere. Solar energy excitation and emission.<br>_Passive_|
|**Ultraviolet**|0.03 to 0.4 mm|Partial absorption by the upper atmosphere (ozone). Few diagnostic features.<br>_Passive_|
|**Visible**|0.4 to 0.7 mm|True and false colour images. Few diagnostic features.<br>_Passive_|
|**Infrared**|0.7 to 100 mm|Reflected solar energy; emitted thermal energy. Many diagnostic features.<br>_Passive_|
|**Near infrared**|0.7 to 1.3 mm|Reflected|
|**Mid  infrared**|1.3 to 3.0 mm|Reflected|
|**Far infrared**|3.0 to 1000 mm|Emitted|
|**Microwave**|0.1 to 100 cm|Penetrates cloud, haze, dust. No atmospheric scattering.<br>_Passive orActive_|
|**Radar**|1.0 to 100 cm|Commonly used in planetary studies.<br>_Active_|
|**Radio**|> 100 cm|Only used for communications; internal gravity studies.<br>_Active_|

# Atmospheric Interactions

- Intensity received inversely proportional to square of distance from sun. • Solar energy at Venus = twice that at Mars

- Presence and composition of atmosphere reduces **surface flux** further.

# Surface Interactions

- The amount of interaction depends on the wavelength of the energy, the material and condition of the feature.

- Remote sensing is concerned with the radiation reflected from targets.

- Spectral reflectance: the portion of the incoming radiation that is reflected.

- Spectral reflectance curve: a graph of the spectral reflectance of an object as a function of wavelength.

<!-- Start of picture text -->
red<br>green<br><!-- End of picture text -->

# Detector Systems

- With few early exceptions, remote sensing systems involve satellite platform + digital detectors.

_Moon: Ranger 9, 24 March 1965, TV camera_

# Detector Systems

- With few early exceptions, remote sensing systems involve satellite platform + digital detectors.

# Detector Systems

##### **Platforms and Orbits**

- Orbital configuration ( **Earth** ); flybys & orbital ( **planetary** )

   - Orbital missions most useful in terms of global studies with repeat coverage

   - Flybys primarily early missions, or first explorations (e.g. New Horizons)

# Detector Systems

###### **Fundamentals**

- Early missions used film, or television → modern = digital

- Digital images amongst most common data set

   - **_Pixels_** = picture elements, numeric value

   - **_Bit (binary digit) depth_** = number of discrete values (controls detail level)

# Detector Systems

##### **Resolution**

- Limit to the level of detail that a detector system can acquire

- Four main types relevant here:

<!-- Start of picture text -->
SPATIAL<br><!-- End of picture text -->

###### **Image Resolution Demonstration 100 m/pixel**

**Image Resolution Demonstration100 m/pixel 50 m/pixel**

**Image Resolution Demonstration 10 m/pixel**

**Image Resolution Demonstration 5 m/pixel**

**Image Resolution Demonstration 1 m/pixel**

**Image Resolution Demonstration 0.1 m/pixel**

# Detector Systems

##### **Resolution**

- Limit to the level of detail that a detector system can acquire

- Four main types relevant here:

<!-- Start of picture text -->
SPECTRAL<br><!-- End of picture text -->

# Detector Systems

##### **Resolution**

- Limit to the level of detail that a detector system can acquire

- Four main types relevant here:

###### **RADIOMETRIC**

4 bit → 2<sup>4</sup> → 16 levels 8 bit → 2<sup>8</sup> → 256 levels 10 bit → 2<sup>10</sup> → 1024 levels 12 bit → 2<sup>12</sup> → 4096 levels

# Detector Systems

##### **Resolution**

- Limit to the level of detail that a detector system can acquire

- Four main types relevant here:

<!-- Start of picture text -->
TEMPORAL<br><!-- End of picture text -->

# Detector Systems

##### **Sensor Mechanics**

- Two main types of detectors:

   **_1. Framing_** . Instantaneous image. Not common in orbital missions.

   **_2. Scanning_** . Narrow FOV, image swept across surface.

      - _Cross-track_ . Scan perpendicular to direction of motion.

      - _Along-track_ . Scan in direction of motion.

# Detector Systems

##### **Planetary**

- Choice of detector depends on both scientific goal and nature of planetary body.

- General trend to use more of EM spectrum, with improving resolution.

- But some exceptions to this trend.

# Detector Systems

- Satellites, aircraft including UAVs.

- RGB (colour) or B&W (greyscale) imagery.

- Optimises spatial detail over spectral information.

# Satellites: Landsat and Sentinel

- ➢ Satellites can image different spectral bands.

- ➢ Some commercial satellites have spatial resolutions of 30-50 cm, while

most non-commercial satellites are 10 -100s m.

- ➢ Temporal resolution varies, weather satellites give images every 5-10 min.

- ➢ European **Sentinel-2** satellites have repeat periods of 3-5 days.

- ➢ USGS/NASA **Landsat** satellites have a repeat period every 32 days.

## Digital multispectral images

- Different bands can reveal different information about the surface features, vegetation, water, or atmosphere.

- Higher spectral resolution means more bands and more diversity, but also more complexity and noise.

- **Landsat** sensors have **8-11** bands, covering the visible, near-infrared, shortwave infrared, and thermal infrared regions.

- **Sentinel** sensors have **13-25** bands, covering the visible, near-infrared, shortwave infrared, and microwave regions.

# Landsat timeline

https://landsat.gsfc.nasa.gov/satellites/timeline/

# Spatial resolution

- ➢ Landsat sensors have a spatial resolution of 15 to 60 metres, depending on the band.

- ➢ Sentinel sensors have a spatial resolution of 10 to 60 metres, depending on the band.

Landsat 8 image of Reykjavik, Iceland, acquired July 7, 2019, illustrating the difference in pixel resolution. Credit: NASA Earth Observatory.

https://www.earthdata.nasa.gov/learn/backgrounders/remote-sensing

# Landsat spectral bands

https://www.usgs.gov/landsat-missions/landsat-9

# Sentinel spectral bands

https://landsat.gsfc.nasa.gov/article/sentinel-2a-launches-our-compliments-our-complements/

<!-- Start of picture text -->
Landsat orbits<br><!-- End of picture text -->

# Image preprocessing: geometric

###### • Geometric correction

- remove geometric distortions caused by sensor-Earth geometry variations.

- georeference the image to a particular projected map coordinate system.

# Image preprocessing: radiometric

###### • Radiometric correction.

- correct an image for sensor response properties and viewing geometry.

- correct an image for atmospheric effects and scene illumination

- restore an image to accurately represent the radiance measured by the sensor.

_True colour (bands 4, 3 and 2)_

<!-- Start of picture text -->
Removing top-of-<br>the atmosphere<br>reflectance<br><!-- End of picture text -->

https://hls.gsfc.nasa.gov/algorithms/atmospheric-correction/

# Image enhancement

#### • Band combination

   - increasing the amount of information that can be visually interpreted.

- Pan-sharpening

   - increasing the spatial resolution of a multispectral image with a higherresolution panchromatic image.

- Contrast stretching

   - enlarging the tonal distinction between different features.

- Spatial filtering

   - enhancing or suppressing specific spatial details.

# Transformation using band combinations

- ➢ _Natural Colour_

(B4, B3, B2) imagery.

- ➢ _Color Infrared_

   - (B8, B4, B3) healthy and unhealthy vegetation.

- ➢ _Short-Wave Infrared_

(B12, B8A, B4) vegetation, bare soil and urban areas.

- ➢ _Agriculture_

(B11, B8, B2) health of crops.

- ➢ _Geology_

(B12, B11, B2) faults, rock types, mineral deposits.

- ➢ _Bathymetric_

(B4, B3, B1) coastal studies, sediment suspension in water.

- ➢ _Vegetation Index_

   - (B8-B4)/(B8+B4) dense canopy, urban and water features.

- ➢ _Moisture Index_ (B8A-B11)/(B8A+B11) identifying water stress in plants, wetter vegetation has higher values. Lower moisture index values suggest plants are under stress from insufficient moisture (drought areas).

# Normalised Burn Ratio (NBR)

_Los Angeles, 2017_

<!-- Start of picture text -->
Eagle Bluff wildfire 31 st  July 2023<br><!-- End of picture text -->

_NBR = (NIR-SWIR) / (NIR+SWIR)_

# Pan-sharpening

A pan-sharpened image combines multispectral and panchromatic images yielding an image with high spectral resolution and high spatial resolution

# Contrast stretching

Original Linear contrast stretching Histogram equalization

### Radio wave detection and ranging (Radar) imaging

- Radar remote sensing = active method using microwave energy.

- Ability to penetrate atmospheres opaque at other wavelengths.

- Interferometric synthetic aperture Radar (InSAR) can measure surface displacements – glaciers, ice sheets, earthquakes – and derive DEMs.

- Longer wavelengths are sensitive to length scales that often reflect differences between geological terrain.

- Intensity of returned radar signal depends on:

   1. Radar system properties (e.g. wavelength, angle, polarization)

   2. Terrain properties (e.g. dielectric properties, surface roughness, orientation)

### Radio wave detection and ranging (Radar) imaging

- Radar not usually nadir – have look direction and depression angle.

- • Records energy as function of time, not distance – image distortions.

### Radio wave detection and ranging (Radar) imaging

<!-- Start of picture text -->
RADAR Foreshortening<br><!-- End of picture text -->

<!-- Start of picture text -->
RADAR Layover<br><!-- End of picture text -->

Magellan: -9.4°, 247.5° Venus

Seasat: Alaska Range Earth

### Radio wave detection and ranging (Radar) imaging

<!-- Start of picture text -->
RADAR Brightness<br><!-- End of picture text -->

Magellan: -58°, 200° Venus

### Radio wave detection and ranging (Radar) imaging

MRO, SHARAD: Mars

### Radio wave detection and ranging (Radar) imaging

ERS-2 SAR interferogram. Izmit, Turkey 1999 Earthquake

# LiDAR elevation masspoints

( **A** ) Top view and ( **B** ) Side view of LiDAR point cloud-based 3D structure of forest canopy.

<!-- Start of picture text -->
DTM<br>DEM<br><!-- End of picture text -->

<!-- Start of picture text -->
DTM<br>DEM<br>DTMs include<br>features above the<br>ground surface<br>DEMs of the bare<br>ground surface<br><!-- End of picture text -->

# Homework and Resources

- ➢ Read Chapter 6 of course textbook: Remote Sensing.

- ➢ Take the quiz to test your basic understanding (on BB).

###### **Further resources**

ESRI training Getting started with spatial analysis (component 1 - 45 min and component 2 - 60 min).

https://www.esri.com/training/catalog/634f16c15030f204ae8e30f4/getti ng-started-with-imagery-and-remote-sensing/

European Sentinel 2 Earth Observation viewer https://www.sentinel-hub.com/explore/eobrowser/

Landsat image viewer

https://landsatlook.usgs.gov/explore

## OCR 补充（原文中无文字层的页面）

_(以下内容由图片 OCR 识别得到，原文件该处无可提取文字；识别可能有误，请对照原件。)_

### Page 38

Landsat orbits

Landsat Next A '

Elapsed: Odays 1.50 hours
