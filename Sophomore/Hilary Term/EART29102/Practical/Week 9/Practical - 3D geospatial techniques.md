---
title: "Practical - 3D geospatial techniques"
source: "Sophomore/Hilary Term/EART29102/Practical/Week 9/Practical - 3D geospatial techniques.pdf"
type: pdf
---

University of Manchester

Geostatistics:  3D visualisation

# Practical: 3D visualisation and analysis of critical mineral deposits beneath Coed-y-Brenin

## <u>Practical aims</u>

Coed-y-Brenin was extensively drilled in the 1960 and 1970s to establish the extent of low grade copper mineralisation.  Samples were taken from the wells and analysed for their metal content.

This practical will use the 3D capabilities of ArcGIS to place the metal concentration values in their correct place below ground.  By completing geostatistical analysis of this extensive dataset you will be able to visualise the extent of the copper deposit.

### Metal rich minerals in Snowdonia

The Harlech Dome area has been a centre for metal exploitation since the mid 1800’s.  130,000 oz of gold has been retrieved along with, lead, silver, manganese and copper.  Copper was mined at Coedy-Brenin, centred on the Glasdir mine which produced about 1300 tonnes until closure in 1914. Closure was partly forced by local campaigns organised to stop degradation of salmon fisheries by the dumping of mine waste into local rivers. If you visit Coed-y-Brenin the ruins of this mining legacy are evident.  Environmental effects are seen in the distribution of metal tolerant plants such as Sea Pinks (Armeria maritima) and Sea-Campion (Silene uniflora) which thrive on mine spoil tips and where metal rich waters reach the surface.

### Geological background

Mineralisation is interpreted to be part of a copper-porphyry system (Mason, Liezers and Cotterell, 2018).  In their scenario a regional scale hydrothermal system was driven by the Rhobell volcanic system during the early Ordovician.  Circulating groundwaters carried metals derived from the volcanic bodies and dissolved from local Cambrian shales of the Mawddach Group.  The metals accumulated in altered, sheared and fractured intermediate volcanic rocks: microtonalite.  The low grade copper mineralisation occurs as chalcopyrite associated with pyrite and disseminated through the rock volume and within small veinlets. Later quartz-carbonate filled veins are larger and associated with pods of both chalcopyrite and molybdenite.  The link to hydrothermal origins are particularly evident in phreato-magmatic explosion breccia pipes found in the upper part of the porphyry. Some of the breccia pipes are significantly enriched in copper, arsenic, gold and tin – the Glasdir mine providing a prime example.

## <u>Practical instructions</u>

### I’m assuming that the class is familiar with ArcGIS pro and it’s operational environment.

### Start project

Open ArcGIS pro and start a new map.  Make sure you have write permission and enough disk space in the location you choose to save the project – about 250 MB.   Name the project:   Coed-y-Brenin

### Set up coordinate framework system

Right click on Map in the ArcGIS Contents Pane and enter Map Properties.

General tab: change map units to meters

Page | 1

University of Manchester

Geostatistics:  3D visualisation

Coordinate Systems tab:

- Horizontal coordinate system:  Enter current XY options and drill down through the menus: Projected Coordinate Systems > National Grids > United Kingdom and select **British National Grid.**

- Vertical coordinate systems: Enter Current Z options and drill through the menus: Vertical coordinate systems > Gravity-related > Europe and select **EVRS2000** :  This is the European Vertical Reference System, which has many variants.

Select OK to apply changes.

### Data import

Download the Practical_files.zip data package from the 3D Spatial Techniques module within Canvas.

Extract contents of zip file. Ensure that the folder structure is maintained so that data files and spatial reference files remain linked together.   Zip file contents:

- Coed-y-Brenin.img:  5m resolution DEM

- Aerial photographs covering Coed-y-Brenin

- Database file (.dbf) of well locations

- Database file of down well mineral grades

Bring each of these into ArcGIS:  Enter the **Map** menu (main toolbars) and click on **Add Data** and one at a time add:

- Add the DEM.

- Add the Well_positions.dbf from within the Well_Data folder.

- A different procedure for the photographs

   - In the left-hand **Contents** pane, right click on **Map** and select **New Group Layer**

   - Right click on the new layer, select properties and change it’s name to **AerialPhotos**

   - Right click on your AerialPhotos layer and select **Add Data**

   - Navigate to the aerial photos.  Select them all (by clicking on the top of the list, holding shift and clicking on the bottom in the list).  Click OK.

   - Note – this is a simple way of putting the aerial photos in a separate folder. They can all be switched on/ off with a single click of the group layer visibility check box.

Well_positions will appear in the contents pane as a data table.  To visualise this within your map: Under the Map tab, in the layer group select **XY Table to Point** .  This will open the geoprocessing dialogue at the right hand of the screen:

- Use the arrow in the input box to select **Well_positions**

- This will add a default file name in the output box: **Well_positions_XYTableToPoint**

- Make sure X, Y and Z fields are defined as BNG_X, BNG_Y and BNG_Z.

- Define the coordinate system in the final box:  the simplest route is to select **Current Map (Map)** which will place the well positions into the same coordinate framework that you set up within the ArcGIS project.

- Click **Run.   Save your project.**

### Convert to 3D view

So far all data has been displayed in a 2D map framework.  To increase the usefulness of data interrogation and allow exploration of the subsurface the map needs to be converted to 3D.  ArcGIS

Page | 2

University of Manchester

Geostatistics:  3D visualisation

offers two options:  Global Scene (national / very large scale datasets); Local scene (small scale projects).  For our purposes Local scene will work best.  To convert:

- From the **View** menu, in the **Windows** group, select **Reset Panes** > **reset panes for mapping.** This will close unused panes and ensure that the contents and catalogue panes are open.

- From the **View** menu, in the **view group** , select **Convert** > **Local Scene** .

ArcGIS will generate a Map_3D window from the data previously loaded into the 2D window.

### To navigate around this window:

- Zoom: Either roll mouse wheel, or move mouse while clicking right mouse button.

- Drag:  move mouse while clicking left mouse button

- Rotate:  move mouse while clicking centre mouse button

## <u>Improve vertical resolution:</u>

ArcGIS uses a default elevation model:  WorldElevation3D/Terrain3D.  This model is based on SRTM data (Shuttle Radar Topography Mission). It is the same 30 meter resolution global database that Google Earth uses.

The Coed-y-BreninDEM file is a terrain model with 5m resolution.  It is currently displayed as a georeferenced raster image where pixel colour corresponds to height.

To use the height information in this file drag Coed-y-BreninDEM into the **ground** section of **elevation surfaces** within the Contents Pane.  Deselect WorldElevation3D/Terrain3D to ensure you are using the higher resolution DTM.

## <u>Investigate critical metals</u>

### Add the metals grades database:

Add the geodatabase: MetalGrade.dbf and display the x,y,z sample positions.  The data only contains the depth below surface recorded by the driller (Depth_m) – use this as the Z field. **Don’t forget to define the correct coordinate system.**

<u>QUESTION:  is this data display fit for purpose?</u>

Turn off layers that mask your view of the xyz data and think about the position of sample points in relation to the ground surface – are they correct?

### Add consistent vertical datum to the sample data

All data was recorded from the same very local datum – the drill floor.  However the drill floor moved from hill top to valley floor within the study area so this measurement is meaningless.  To better relate the metal grade values we need to convert the sample position data to heights above sea level by joining the MetalGrade and Well_Positions tables.  To do this:

1. Right click on the MetalGrade standalone table in the Contents panel and choose **Open** .  The associated data table shows how data is arranged in columns (Data fields).

2. Click on **Field:  Add** (just above the table that opens) **.** This will enable creation of a new field to store sample heights.  Change the parameters in this new field, clicking enter to set each one:

   - Field Name:  Height_m

Page | 3

University of Manchester

Geostatistics:  3D visualisation

- Data Type:  Float (this defines that the values stored in the column will be numbers of up to 6 decimal places).  Double precision would be more precise, but also use unnecessary memory.

- Number format:  Numeric (define that the values are numeric).

3. **Save** the new field – this option should be present in the context sensitive menu in the main **Fields** menu.  Close the Fields view.

4. Next, join the Well_positions and Metal_Grade tables to give access to both the xyz position of each drill position and the down well depths:

5. Right click on the MetalGrade table in the Contents panel and select **Joins and Relates** > **Add join.** Input parameters:

   - Input table:  Metal_Grade (first Database)

   - Input field: Borehole (this field is common to both databases and will be used to ‘join’ the tables)

   - Join table:  Well_Positions (related database)

   - Join table field:  Borehole

6. Join operation:  Join one to first

7. **Validate Join** (there is an error as one of the databases has no index, but this is not a problem),  click **OK** .

Page | 4

University of Manchester

Geostatistics:  3D visualisation

8. Joining the databases has populated the BNG x, y and z fields for the drill position for each of the borehole positions. We can use this to calculate absolute heights for the sample positions by adding the well position height (BNG_Z) to the down well sample position (Depth_m).

   - Right click on the header of the Height_m field you previously generated.

   - Select **Calculate field**

   - Find MetalGrade.Height_m = at the bottom of the calculate field dialogue. We will fill this with values selected from this window.

   - First, find Well_positions.BNG_Z in the left-hand **fields** dialogue and double click to add to the calculation dialogue and add (+) this to MetalGrade.Depth_m

   - i.e. **Metal_Grade.Height_m =  !Well_Positions.BNG_Z! + !Metal_Grade.Depth_m!**

   - Select **OK and save the table.**

   - A visual inspection of the new content of the field should show decreasing height corresponding with increasing well depth.

9. To finish, right click on the Metal-Grade table and select **Joins and Relates** > **Remove all joins.** This is a necessary step because joined tables cannot be plotted.

   - In case of error, export your new table with the additional **Height_m** column:

   - Right click on Metal_Grade in the Contents pane. Select Data > Export Table

   - Provide a logical name for your output table and select OK.  Arc should add this new table to your project – if not manually add it using **Map** > **Add data** .

10. Select your modified table and select **display XY data.** Use your calculated Height_m field

for Z values and the correct coordinate system.  Disable / delete the old copper x,y values to avoid confusion. (Note – it is possible the Height_m field became linked to the original Metal_Grade table – check here if it is missing).

11. To finish this step, visualise the copper grade of the points using the symbology dialogue.

   - Open the symbology of the MetalGrade point file by right clicking in the contents pane.

   - Enable graduated colours for the **Cu_percent** field

In the resultant colouring of feature points, the warm colours represent higher copper grade.  This is a basic view of the ore body. To get a better view, geostatistical methods can be employed to predict a 3D volume (filling in the space between point measurements).

Page | 5

University of Manchester

Geostatistics:  3D visualisation

## <u>Preliminary geostatistical investigation of the orebody:</u>

Select the metal grades standalone table in the contents pane:

In the **Analysis** menu, select **Data Engineering** in the **Workflows** group.

Select the Cu_Percent field and drag it into the analysis window and click **calculate** .  Fill in the following statistical parameters:

- Mean:  _________________  (the arithmetic mean of Cu_percent values)

- Median:  _______________  (the value that lies centrally in an ordered list of Cu values)

- Mode:   ________________  (the value that occurs most frequently)

Arrange the types of statistics in order:

________________  >  ___________________  >  ___________________

Question:  What do the relative values of mean, mode and median tell you about the resource?

Interpolate Borehole Data

You have previously used 2D geostatistical methods to investigate relationships between data points. The same methods can be expanded into 3D.

- We are going to use **Analysis** > **Geostatistical Wizard** .

- Select the **Empirical Bayesian Kriging 3D** Tool.

(Licensing errors will be caused if 3D Analyst and spatial Analyst are not enabled).

Input dataset:

- Source dataset:  your new Metal_Grades XYTableToPoint point file that includes height data.

- Elevation field:  Height_m

- Data Field:  Cu_percent

- Click Next

- Continue through the dialogue using defaults for all options.

Take note of the semi-variogram, which displays the results of data correlation.

Page | 6

University of Manchester

Geostatistics:  3D visualisation

## <u>The semi-variogram</u>

<!-- Start of picture text -->
• Sample variogram (Observed) plot of changing variance as lag<br>distance increases.<br>• Variogram model (Empirical): mathematical expression used to<br>describe the sample variogram.<br>• Lag distance: the direction dependent distance between data<br>points.<br>• Semi-variance: half the variance of the differences between all<br>possible points spaced a constant distance apart.<br>• Range:  The point where increasing lag distance no longer has<br>an effect on semi-variance.<br>Figure 1.  Fundamentals of the variogram: an<br>estimation of the dependency of pairs of data  • Nugget: semi-variance where separation distance between<br>points with increasing separation distance (lag  samples is zero.  In a perfect dataset the variogram model<br>distance), used by ArcGIS to fill areas of  would cross the y-axis at 0. Measurement error and Gaussian<br>unknown data.   distribution of natural data means it will have some variance.<br><!-- End of picture text -->

<!-- Start of picture text -->
Semi-variance<br><!-- End of picture text -->

<!-- Start of picture text -->
nugget<br><!-- End of picture text -->

<!-- Start of picture text -->
Empirical semi-variances<br><!-- End of picture text -->

<!-- Start of picture text -->
Lag distance (distance between data points)<br><!-- End of picture text -->

_Figure 2. The 3D Empirical Bayesian Kriging process is different. It divides the data into subsets of points (default is 100 points), to estimate a series of semi-variograms.  These semi-variograms are used to simulate data at the input points. This new data is used to estimate a new semi-variogram and the process repeated a set number of times. This generates a large number of semi-variograms (blue lines).    ArcGIS makes sense of it by binning the data into pairs of points with common lag distance and direction.  These empirical (experimental) semi-variances are plotted as blue crosses._

## <u>Results</u>

3D kriging generates horizontal slices from the data. The results can be browsed using the vertical slider to the right of the main screen.   To view in 3D we need to convert the Krig results to a Voxel Layer.

Page | 7

University of Manchester

Geostatistics:  3D visualisation

<u>Export your 3D krig results to a Voxel Layer Using the GA Layer 3D to NetCDF Tool</u> Right click on the Empirical Bayesian Kriging 3D results in the contents pane. Select Export **to NetCDF/Voxel** tool. Navigate to your file location and name it Cu_voxels.

Note:  Output of the GA Layer to NetCDF tool is not always automatically added to the local scene. You may need to use **Add Data** to add it to your local scene as a Multidimensional Voxel Layer.

You should have something like this:

## <u>To visualise the economic orebody geometry:</u>

Results filtering:  The ore handling facilities are unable to process ore containing less than 0.2% grade. This is considered the economical limit, returning approximately 2 kg of copper per tonne of ore mined.  To visualise the economic copper:

- Select the voxel layer in the file tree. The object specific toolbar will appear.

- Select ‘Voxel Layer’

- In the drawing group, click on ‘Symbology’ to open the symbology for the voxel layer. Display is based around the data histogram for copper grade.  Note the shape of the histogram: it is skewed to the right which is what you probably predicted from calculation of mode, median and mean.  Note: Mode demonstrated that most of the dataset is below economic grade.

Above the histogram select ‘data filter’ and use the slider (or input box) to remove voxels that represent uneconomical copper.  You should now have something like this:

## <u>Troubleshooting visualisation issues</u>

If the computer has issues displaying and manipulating in 3d space, try reducing the CPU load.

In the main window click on the PROJECT tab.  Drill down to OPTIONS in the left hand menu.  Find the DISPLAY options and try:

- Antialiasing mode:  switch to normal or none

- Rendering quality:  slide to low

- Maybe switch to the OpenGL rendering engine

Page | 8

University of Manchester

Geostatistics:  3D visualisation

## <u>Final Analysis</u>

Geology:  The copper mineralisation mostly occurs in microtonalite intrusives.

What type of intrusion is this?  Assess intrusion shape by isolating copper display to the highest concentrations which occur around the intrusion edges.  Is this geometry helpful for extracting minerals?

The model displays the distribution of exploitable copper in the subsurface below Coed-y-Brenin.  If the copper body was to be mined, how destructive would it be to Snowdonia?

i.e. use the measure tools to estimate how deep and wide the open cast pit would need to be.

## <u>If you have time at the end of the practical:  some extra tasks:</u>

### Additional critical minerals

Distinct zones develop within copper porphyry systems (Silitoe 2010).  As magmatic driven hydrothermal fluids pass upwards through the rock volume they develop a central zone where copper becomes concentrated as copper sulphides.  Outside this is a halo enriched in pyrite (iron sulphide).  Separate hydrothermal phases may also deposit other metal rich phases.

The metal grades database contains values for pyrite (Ss), molybdenum (Mo) and gold (Au).  Plot these within your 3D model to investigate how they relate to the main copper ore body.

Gold:  values are in ppm. Economic grade is 0.5 ppm. Molybdenum: values listed as percentages. Economic grade is about 0.05%.

_Figure 3. Blue: central core enriched to greater than 0.2% copper. Pink: pyrite rich (>1.5%) halo._

### Alternative methods for visualising subsurface data.

### Surfaces, Isosurfaces and slices

There are other ways of interacting with voxel layers.  By expanding the Voxel layer in the content panel, it is possible to use various slicing and isosurface techniques.  Experiment with the options by right clicking and selecting **create new.**

Note: an isosurface is a surface of equal value. It can be used to set and isolate the outer boundary of the ore body.

Page | 9

University of Manchester

Geostatistics:  3D visualisation

## <u>References</u>

Mason, J.S., Liezers, M., Cotterell, T.F. 2018. Andradite-bearing skarn-like mineralisation and a suspected palaeogene dyke from Coed y Brenin, North Wales. Journal of the the Russell Society v.21, p.106–123.

Sillitoe, R.H. 2010. Porphyry Copper Systems. Economic Geology. V.105: p.3–41.

Page | 10
