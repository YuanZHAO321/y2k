---
title: "Palaeocurrent exercise"
source: "Sophomore/Michaelmas Term/EART27201/Practical/Week 5/Palaeocurrent exercise.pdf"
type: pdf
---

# **Class 5 homework exercise**

# **Palaeocurrent Data Analysis**

_Accuse not Nature, she hath done her part; Do thou but thine_

Milton, Paradise Lost

# Introduction

In Earth Sciences the directions or orientations of objects or structures are frequently of major interest.  For example, the orientation of woody debris on a bedding surface can provide information about the direction of the currently operating when they were deposited, known as the palaeocurrent direction.  Palaeocurrents can be determined from a variety of fabrics, bedforms and sedimentary structures.  The study of palaeocurrents is an important component of an analysis of the rock record, as they allow us to determine things like the sediment transport direction, basin geometry, and source area location.

In many cases when dealing with palaeocurrent data from the rock record it is necessary to correct the data for any tectonic tilt that has occurred subsequent to deposition in order to determine the original current direction.  In this exercise you will only use data that has already been corrected.

At the end of this exercise you should be able to calculate the various statistics used in the analysis of palaeocurrent data and to construct rose diagrams

# **a) A qualitative description of the data: plotting rose diagrams**

A _rose diagram_ is a circular histogram.  It is constructed by sorting the data into bins _x_<sup>0</sup> wide (where 360/ _x_ is a whole number) from 0<sup>0</sup> through to 360<sup>0</sup> and then by plotting a graph showing each bin as an _x_<sup>0</sup> segment of a circle, with a radius proportional to the number of data in that particular bin (Figure 1).

Figure 1 Example of directional data plotted as a conventional histogram and a rose diagram (inset). (after Cheel, 2006)

When the radius of each segment in a rose diagram is proportional to frequency, the diagram visually overemphasises high frequencies (Figure 2a).  This is because the visual impression of a segment is proportional to its area which is proportional to radius squared, not radius.  Many people argue that a visually more accurate representation is given by making the radius of each segment proportional to the square root of the frequency (Figure 2b).

Figure 2 Illustration of how a frequency rose diagram visually overemphasises high frequencies because the visual impression is proportional to area; plotting as root frequency avoids this issue.

The distribution of data may have one or more modes, and is called unimodal if one mode is present, bimodal if two modes are present (bipolar if the modes are at 180<sup>0</sup> to each other) or polymodal if more than two modes are present (Figure 3).  The data may vary symmetrically or asymmetrically about the mode(s).

Figure 3 Types of palaeocurrent pattern, plotted as rose diagrams (after Pettijohn, Potter and Siever, 1973)

# **b) Calculating the mean direction and a measure of dispersion**

In almost all cases where directional data are used it is necessary to collect a large number of measurements to derive at least a reliable (if not statistically significant) picture of palaeocurrents in ancient depositional environments.

If many orientation measurements have been made at a given locality, it is of interest to determine the mean orientation.

Directional data are specified in terms of angles, which mean that the mean orientation cannot be determined in the usual way (i.e. by adding up all the angles and dividing by the number of measurements) (Figure 4).  For example, if we have two directional measurements, one on a bearing of 001<sup>0</sup> and the other on a bearing of 359<sup>0</sup> , both are approximately due north, and yet the usual method for determining the mean of the two measurements gives us (1<sup>0</sup> +359<sup>0</sup> )/2=180<sup>0</sup> , which is due south.  To avoid this problem, the mean direction must be determined using trigonometric functions because such functions repeat every 360<sup>0</sup> .

Figure 4 Example of the derivation of a resultant vector (large arrow) by the summation of the unit vectors (small numbered arrows).  Each unit vector shown has the direction shown and a magnitude (ri).  Note that the arithmetic mean would be 146<sup>0</sup> and clearly not representative of the three vectors.

# **_Method_**

If the data are stated as the angles  1,  2, ....  n, then they may also be represented by the unit vector with components

so that the resultant vector incorporating all the measurement has components

The mean direction is then

Using a calculator or computer to determine this mean direction when the angle is specified in degrees (not radians) will return a value in the range -90<sup>0</sup> to 90<sup>0</sup> whereas the actual result will be in the range 0<sup>0</sup> to 360<sup>0</sup> .  The correct value can be found by adding either 0<sup>0</sup> , 180<sup>0</sup> or 360<sup>0</sup> to the returned value according to the signs of the _x_ and _y_ components:

if _x_ r is positive and _y_ r is positive add 0<sup>0</sup> if _x_ r is positive and _y_ r is negative add 180<sup>0</sup> if _x_ r is negative and _y_ r is negative add 180<sup>0</sup> if _x_ r is negative and _y_ r is positive add 360<sup>0</sup>

The circular variance of the data is determined from the length of the resultant vector,

The circular variance so-defined has a range of 0 to 1, where 0 indicates that all the directions are identical.

# **_Exercise 1_**

The following data are palaeocurrent measurements inferred from ripples and scours/flutes from the tops and bottoms of beds at a location.  The data have been corrected for the dip of the units so that each figure is the compass bearing of the direction of current flow at the locality where the observation was made at the time when the units were being deposited.

# Ripples (top of beds)

046<sup>0</sup> , 241<sup>0</sup> , 290<sup>0</sup> , 260<sup>0</sup> , 251<sup>0</sup> , 249<sup>0</sup> , 278<sup>0</sup> , 295<sup>0</sup> , 297<sup>0</sup> , 316<sup>0</sup> , 314<sup>0</sup> , 326<sup>0</sup> , 309<sup>0</sup> , 254<sup>0</sup> , 251<sup>0</sup> , 224<sup>0</sup> , 259<sup>0</sup> , 238<sup>0</sup> , 248<sup>0</sup>

Scours/flutes (bottom of beds)

242<sup>0</sup> , 239<sup>0</sup> , 240<sup>0</sup> , 253<sup>0</sup> , 235<sup>0</sup> , 258<sup>0</sup> , 272<sup>0</sup> , 239<sup>0</sup> , 088<sup>0</sup> , 175<sup>0</sup> , 200<sup>0</sup> , 031<sup>0</sup>

1. Ripples.  Enter the palaeocurrent data into the first column of Table 1.  Group the ripple data into bins 10<sup>0</sup> wide from 0<sup>0</sup> to 360<sup>0</sup> in Table 1 (e.g. so that the first bin is 0<sup>0</sup> to 9<sup>0</sup> , the second is 10<sup>0</sup> to 19<sup>0</sup> , and so on).  Now plot a graph showing each bin as a 10<sup>0</sup> segment of a circle, with a radius proportional to the **square root** of the number of data in that particular bin.

Ripples

Mean direction = Variance =

# **Repeat this procedure for the scour/furrow data**

Scours/flutes

Mean direction = Variance =

2. Determine the mean direction and variance of the palaeocurrent data given above.  The maths for doing this is outlined on a previous page of this handout.  Use Tables 1 and 2 to organise your calculations.

   - i. Calculate sin  and cos  for each palaeocurrent reading.

   - ii. Using a calculator, you need to calculate:

      - a. _xr_ by summing all the sin  values

      - b. _yr_ by summing all the cos  values

      - c. Mean direction (remember to correct the mean so that it falls between 0<sup>0</sup> and 360<sup>0</sup> )

      - d. Circular variance

   - iii. Show the resultant values on your plots.

3. How would you describe the palaeocurrent pattern for each plot (see p. 2 for correct terminology)?

4. Compare the two data sets and note that the ripple data was obtained from the top of the beds and the scour data came from the bottom of the beds.  What can you infer about flows that formed the two sets of data?

5. Plot the two mean palaeocurrent directions on your map using arrows.  Remember to add the symbol to the map key.

# **_Exercise 2_**

The following angles are the azimuthal orientations of a number of elongate shells exposed in a horizontal bedding surface.

075<sup>0</sup> , 255<sup>0</sup> , 180<sup>0</sup> , 025<sup>0</sup> , 170<sup>0</sup> , 195<sup>0</sup> , 050<sup>0</sup> , 250<sup>0</sup> , 130<sup>0</sup> , 020<sup>0</sup> , 025<sup>0</sup> , 005<sup>0</sup> , 175<sup>0</sup> , 190<sup>0</sup> , 335<sup>0</sup> , 180<sup>0</sup> , 195<sup>0</sup> , 195<sup>0</sup> , 010<sup>0</sup> , 070<sup>0</sup> , 150<sup>0</sup> , 185<sup>0</sup> , 180<sup>0</sup> , 005<sup>0</sup> , 025<sup>0</sup> , 205<sup>0</sup> , 210<sup>0</sup> , 025<sup>0</sup> , 040<sup>0</sup> , 190<sup>0</sup> , 190<sup>0</sup> , 180<sup>0</sup> , 035<sup>0</sup> , 020<sup>0</sup> , 005<sup>0</sup> , 260<sup>0</sup> , 185<sup>0</sup> , 200<sup>0</sup> , 175<sup>0</sup> , 230<sup>0</sup> , 235<sup>0</sup> , 025<sup>0</sup> , 045<sup>0</sup> , 245<sup>0</sup> , 050<sup>0</sup>

1. Enter the data into the first column of Table 3.  Group the data into bins 30<sup>0</sup> wide from 0<sup>0</sup> to 360<sup>0</sup> in Table 3. Now plot a graph showing each bin as a 30<sup>0</sup> segment of a circle, with a radius proportional to the square root of the number of data in that particular bin.

2. How would you describe the palaeocurrent pattern of the plot?  Is it unimodal or bimodal?

The plot shows a bimodal distribution, not a unimodal distribution.  In order to be able to calculate the mean and variance of the data it is necessary to treat the measurements as a line of movement, rather than direction of movement.  In order to use the formulae given, you must first put all data in the same hemisphere.  In this case, subtract 180<sup>0</sup> from all azimuths greater that or equal to 180<sup>0</sup> .

To see the importance of thinking about (and plotting) the spread of data _before_ calculating the mean, do the following:

3. Calculate the mean direction for the data using the data in the form it is given (column 1, Table 3).

Mean direction =

4. Now subtract 180 from all readings greater or equal to 180<sup>0</sup> (enter the values into 'Modified data' column).  With your new data set determine the mean direction and variance.

Mean direction =

Variance =

Compare the two mean with the plot and make sure you understand.

# **Summary: Interpretative pointers**

1. Beware observer bias in interpreting the data, particularly in small data sets (more data from certain horizons or localities where it is easy to collect the data)

2. Separate/analyse the data by stratigraphic position (look for changing current directions with time). Plot the data on a graphic log.

3. Analyse data by locality (look for changing current directions with place).  Plot the data on a map.

4. Bear in mind how the palaeocurrent indicator was formed.  Compare current directions from underside and top of beds.

5. Plot data for the _direction of flow_ as an arrow on a map, and for the _line of flow_ plot it as a double

headed arrow

e.g.,                     versus

Table 1 Ripples

|Data ()|sin|cos|Bin|Frequency|Frequency<sup>1/2</sup>|
|---|---|---|---|---|---|
||||0|||
||||10|||
||||20|||
||||30|||
||||40|||
||||50|||
||||60|||
||||70|||
||||80|||
||||90|||
||||100|||
||||110|||
||||120|||
||||130|||
||||140|||
||||150|||
||||160|||
||||170|||
||||180|||
|sum|||190|||
||||200|||
||||210|||
|Mean (0-360<br>degrees)|||220|||
||||230|||
||||240|||
|**circular variance**|||250|||
||||260|||
||||270|||
||||280|||
||||290|||
||||300|||
||||310|||
||||320|||
||||330|||
||||340|||
||||350|||
||||360|||

Table 2 Scours/Flutes

|Data ()<br>sin|cos|Bin|Frequency|Frequency<sup>1/2</sup>|
|---|---|---|---|---|
|0.00|1.00|0|||
|0.00|1.00|10|||
|0.00|1.00|20|||
|0.00|1.00|30|||
|0.00|1.00|40|||
|0.00|1.00|50|||
|0.00|1.00|60|||
|0.00|1.00|70|||
|0.00|1.00|80|||
|0.00|1.00|90|||
|0.00|1.00|100|||
|0.00|1.00|110|||
|sum||120|||
|||130|||
|||140|||
|Mean (0-360<br>degrees)||150|||
|||160|||
|||170|||
|**circular variance**||180|||
|||190|||
|||200|||
|||210|||
|||220|||
|||230|||
|||240|||
|||250|||
|||260|||
|||270|||
|||280|||
|||290|||
|||300|||
|||310|||
|||320|||
|||330|||
|||340|||
|||350|||
|||360|||

Table 3 Elongate shells

|Data ()<br>sin|cos|Modified data ()|sin|cos|Bin|Frequency|Frequency<sup>1/2</sup>|
|---|---|---|---|---|---|---|---|
|0.00|1.00||0.00|1.00|0|||
|0.00|1.00||0.00|1.00|30|||
|0.00|1.00||0.00|1.00|60|||
|0.00|1.00||0.00|1.00|90|||
|0.00|1.00||0.00|1.00|120|||
|0.00|1.00||0.00|1.00|150|||
|0.00|1.00||0.00|1.00|180|||
|0.00|1.00||0.00|1.00|210|||
|0.00|1.00||0.00|1.00|240|||
|0.00|1.00||0.00|1.00|270|||
|0.00|1.00||0.00|1.00|300|||
|0.00|1.00||0.00|1.00|330|||
|0.00|1.00||0.00|1.00|360|||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|0.00|1.00||0.00|1.00||||
|sum||sum||||||

 Mean (0-360 degrees)

 Mean (0-360 degrees)

**circular variance**

**circular variance**
