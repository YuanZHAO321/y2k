---
title: "SubsidenceAgeProject2025_withNeilMitchell"
source: "Sophomore/EART29200/SubsidenceAgeProject2025_withNeilMitchell.pdf"
type: pdf
---

# **EART29200 2nd year tutorials project with Neil Mitchell: Earth's heat loss and the variation in water depth with oceanic crustal age**

The purpose of this tutorial exercise is to develop your skills in developing a scientific report, and to develop your appreciation of the distinction between models and data.  You will generate your own datasets using a data browsing tool called GeoMapApp and analyse them to understand how heat loss from the Earth's interior affects the shapes of the ocean basins.  The report should contain an abstract, introduction, methods, results, discussion, conclusion and references.

Why engage with this subject?  If you eventually choose petroleum geoscience for your careers, this type of analysis is important because the temperatures of rock formations determines whether organic matter turns into gas or oil.  Indeed, a version of the model developed by McKenzie (1978) has been highly influential and further modified versions of it get used in petroleum exploration.  "Diffusion" (part of the analysis below) also occurs in many other studies, such as how fluid flows through rocks, spreading of soluable elements in aquifers, even the movement of soil on slopes (geomorphology).  You will find "linearization", which we use below, also appears in many area of geoscientific data analysis.

## **Background: how Earth loses heat**

We can measure how fast different rocks pass heat by attempting to heat it up on one side and seeing how fast a water body on the other side heats up.  This is illustrated by Figure 1.

Figure 1: Schematic diagram of experimental apparatus used to measure heatflow through rock samples.

A disc of rock (brown) is heated on the left side, increasing the water temperature T1.  At the other side of the disc, further water starts to warm up from the heat travelling through the rock, hence T2 (which can be measured) increases.  We know the heat energy that has been conducted through the rock from the increase in T2 and the heat capacity of the water on the right side.  The passage of heat energy is expressed mathematically:

Q is the rate at which heat energy is transferred (W/m<sup>2</sup> ), DT/Dx is the temperature gradient across the disc (˚/m) and k is the rock's thermal diffusivity (how conducting it is) in W/˚/m. Hence, the experiments are used to find out k as the other variables can be measured. (Why is there a minus sign in equation (1)?)

Figure 2: Spreading apart of the Earth's tectonic plates at mid-ocean ridges (source unknown).

At mid-ocean ridges, the rocks are hot and the boundary between the more solid part (the lithosphere) and the more ductile part (the asthenosphere) is near the surface.  The mantle spreading sideways from there cools down, following equation (1).  Researchers have used measurements of k and the heat capacity of the rocks to work out how the lithosphere thickens and the upper mantle cools down.  As the upper mantle becames "older" and cooler, it contracts, becoming denser.  Hence, it sinks over the more ductile asthenosphere underneath.

Parsons and Sclater (1977) used equation (1) and the properties of mantle rocks to suggest that the top of the oceanic lithosphere follows a simple equation:

where t is age (Ma). Parsons and McKenzie (1978) derived a two layer model in an attempt to explain the relationship in older oceanic crust. Their model had an upper mechanically rigid layer (the lithosphere) and a lower viscous thermal boundary layer (asthenosphere):

However, the systematic relationships between ocean depth and heat flow with age are not well described by these models for old oceanic lithosphere. Therefore, Stein and Stein (1992) determined the following specific relationships for young and old oceanic crust to better describe the observed variation from the predicted values for older crust:

5.0 for younger crust _depth_ ( _km_ ) = 6.2 + .0365 _t_ (4) for older crust _depth_ ( _km_ ) = .5651 - .2473.exp(-.00278 _t_ ) (5) -2 -5.0 and for younger crust _heat flow_ ( _mWm_ ) = 510 _t_ (6) for older crust _heat flow_ ( _mWm_ -2 ) = 48 + 96.exp(-.00278 _t_ ) (7)

Your task will be to determine whether or which of these mathematical models "explains" the variations in the dataset that you will derive.

# **Starting to use GeoMapApp**

G _eoMapApp_ is an application that provides an interface to a large collection of geological and geophysical data collected worldwide, as well as some simple data analysis tools. _Geomapapp_ can be found at the following location _,_ http://www.geomapapp.org/. Download the Java application to your desktop and double-click on the application's icon to launch it (if your Java is out-of-date you may be asked to update it).  On a Mac, you would download it to your applications folder and also double-click the icon to start it.  Click "accept" on the window that appears.

To begin with, have a browse through the options available under the upper tabs once the main window has loaded.  Under **DataLayers** , you will see various global and local grids, such as elevations from the Space Shuttle radar, bathymetry derived from combined altimetry and shipboard soundings, geophysical grids (gravity, magnetics…).  There are also pointwise data, such as earthquake locations and heat-flow measurements.  Under **Portals** , you'll see various data hosted by other sites. **FocusSites** contains various data derived from mainly NSF-funded programmes. **Overlays** can be useful when making a final map.

If you are using _Geomapapp_ from a computer with a small screen or with a tracker pad and find the menus difficult to navigate, click the "Click for searchable tear-off menus" that appears under the top set of menus.

Initially, the browser will only show images of the global topography, whereas you will need the actual data in order to carry out an analysis.  To load into your computer the relevant grids, go to "DataLayers" (top-left option), then "Bathymetry and Topography models", then "Global Models", then select the GMRT (4th option down).  Then similarly select DataLayers -> Geophysics -> Lithospheric Plates -> Crustal age grid (Muller 2008 v3).  If you want to see both datasets at the same time, change the opacity within the Layer Manager Window.  It can also be used to change the order the grids appear on your screen.  If you click on the "i" icon within that window, you should be taken to a web page that contains some information on the layer.

To make cross-sections, select the "Distance/Profile Tool" (second-row, top-left).  When you click on the map, drag the cursor and then release it, you will see a cross-section window appear containing both data types.  You can then save it using the button top-left within that window.  You can save it simply as an image, though we need the data so instead pick "Save ASCII table".  You should be able to read this files into Excel or other software to do your analysis.

# **Choosing where to make cross-sections**

You may wish to make at least three cross-sections that should illustrate different effects. One could be in the east Pacific, where the East Pacific Rise is spreading very quickly. Another could be in the Atlantic, where the Mid-Atlantic Ridge is spreading more slowly.  A third one could be on the Reykjanes Ridge south of Iceland, where the ridge is unusually shallow - this is because the ridge is near the Iceland mantle hotspot (why would the ridge be shallow and why might the trends expected from the subsidence equations be different there?).  You should see many giant hills on the seabed in both areas.  These are called "seamounts" and are produced by volcanism mostly.  Should we include or avoid them? You should also see giant lines cross both the Atlantic and Pacific Oceans (relatively straight but curving in places).  These are called "fracture zones" produced where the ridge is offset laterally.  Wilson (1965) first suggested that these were caused by strike-slip movements between ridge segments required from geometry (Figure 3).

Figure 3.  How fracture zones formed (from Wilson (1965)).

Do we need to make our cross-sections parallel or perpendicular to these fracture zones?

For each cross-section, load the dataset into Excel to have a quick look (Open -> delimited (tab-delimited should work).  Organise your data columns so that you have age in one column followed by elevation in a second column.  Select those columns and chose Insert -> scatter graph.

# **Analysing your dataset**

First, take a look at equations 2 to 5.  See what equation (2) would predict by adding another column in your Excel file and include in one cell a version of equation (2).  You would type "=-(2500+350*[A]^0.5)" ([A] is a link to the cell containing the age).  Overlay that predicted-depth column on your graph and compare it to your data.  You might try the other model predictions also.  Can you tell which of these trends best explains the variations in your datasets?  Hopefully, you will see that it can be difficult to tell, hence we need another method to analyse data.

In many scientific problems, we expect some property to vary with other properties following either of two types of equations:

(A and B are constants, and "e" is a special number with the value 2.7....)

Notice that we can turn these equations into forms that are like "Y=mx+C" (a straight line) by taking logarithms.  Doing so for (6) and (7) produces:

See how you can change equations 2 to 5 into straight-line equations and apply them to your data also.  You will use your results along with the simple graphs to develop your reports.  I am not expecting you to generate results for the heat-flow equations (6 and 7) though we can explore them if we have time.

Your reports should be professionally produced.  Hence, sources of information should be properly cited and referenced.  Figures should be numbered with captions placed below each one.  There is no need to include the data as tables (though if you do include tables follow usual practice of giving them each a number and giving a title above each table). Your text should be written in the 3rd person, passive voice ("A cross-section was drawn ..." not "I drew a cross-section").

You are strongly advised against using AI for this report as you need to develop scientific writing skills (this would be needed if you were to use AI in a job effectively).  However, if you do use AI, you must follow University rules in declaring its use.  University plagiarism rules also apply.

# **References**

- Crosby, A.G. and McKenzie, D., 2009. An analysis of young ocean depth, gravity and global residual topography. Geophys. J. Int., 178: 1198-1219.

- McKenzie, D.P., 1978. Some remarks on the development of sedimentary basins. Earth Planet. Sci. Lett., 40: 25-32.

- Müller, R.D., Sdrolias, M., Gaina, C. and Roest, W.R., 2008. Age, spreading rates, and spreading asymmetry of the world's ocean crust. Geochem. Geophys. Geosyst.,, 9: paper Q04006, doi:04010.01029/02007GC001743.

- Parsons, B. and McKenzie, D.P., 1978. Mantle Convection and the thermal structure of plates. J. Geophys. Res., 83: 4485-4496.

- Parsons, B. and Sclater, J.G., 1977. An analysis of the variation of ocean floor bathymetry and heat flow with age. J. Geophys. Res., 82: 803-827.

- Stein, C.A. and Stein, S., 1992. A model for the global variation in oceanic depth and heat flow with lithospheric age. Nature, 359: 123-137.

- Wilson, J.T., 1965. A new class of faults and their bearing on continental drift. Nature, 207: 343-347.
