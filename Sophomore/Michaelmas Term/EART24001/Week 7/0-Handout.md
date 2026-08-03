---
title: "0-Handout"
source: "Sophomore/Michaelmas Term/EART24001/Week 7/0-Handout.pdf"
type: pdf
---

# **Means of directional measurements**

In geology the orientations of objects or structures are frequently of major interest. The particular characteristic of such data is that they are measured in terms of angles. Angles require special methods of analysis when calculating means: if we have two directional measurements, one on a bearing of 001° and the other on a bearing of 359°, both are approximately due north, and yet a simple arithmetic mean of the two gives us (1 + 359)/2 = 180°, which is due south. To avoid this problem, averaging of angles is carried out using trigonometric functions because such functions repeat every 360°.

## **A qualitative description of the data: plotting rose diagrams**

- A rose diagram is a circular histogram. It is constructed by sorting the data into bins _x_ ° wide (where 360 / _x_ is a whole number) from 0° through to 360° and by then plotting a graph showing each bin as an _x_ ° wide segment of a circle with a radius proportional to the number of data in that particular bin

- The look of a rose diagram is sensitive to the choice of bin width. This choice depends on the spread of data but a helpful guide is given by

here _R_ is the range of the data ( _e.g._ , 360° but it might be smaller than this if the data occurs only over a limited angular range), and _n_ is the number of data.

- When the radius of each segment in a rose diagram is proportional to frequency, the diagram visually overemphasizes high frequencies. This is because the visual impression of a segment is proportional to its area, and this is proportional to radius squared, not radius. A visually accurate representation is given by making the radius of each segment proportional to the square root of frequency

## **Calculating the mean direction and a measure of dispersion**

- If the data are stated as the angles, _θ_ 1, _θ_ 2, . . . _θn_ , then they may also be represented by the unit vector with components

so that the resultant vector incorporating all the measurements has components

The mean direction is then

Note that when the angle is specified in degrees (not radians) the mean direction returned will be in the range -90° to 90° whereas the actual result must be in the range 0° to 360°. The correct value can be found by adding either 0°, 180° or 360° to the returned value according to the signs of the _xr_ and _yr_ components:

if _xr_ is positive and _yr_ is positive add 0° if _xr_ is positive and _yr_ is negative add 180° if _xr_ is negative and _yr_ is negative add 180° if _xr_ is negative and _yr_ is positive add 360°

- The circular variance of the data is determined from the length of the resultant vector,

𝑐𝑖𝑟𝑐𝑢𝑙𝑎𝑟 𝑣𝑎𝑟𝑖𝑎𝑛𝑐𝑒  =   1 −  �(𝑥�<sup>�</sup> + 𝑦�<sup>�</sup> )<sup>�/�</sup> / 𝑛�

The circular variance so-defined, has a range of 0 to 1, where 0 indicates that all directions are identical.

- NB. if the directional data is bidirectional not unidirectional ( _e.g._ , line of flow not direction for flow), the above formulae may still be used but only after correcting the data to the same end of the line of flow.

## **Further reading**

>  Borradaile, G., 2003, _Statistics of Earth Science Data: Their Distribution in Time, Space, and Orientation_ . Springer

- Sanderson DJ, Peacock DCP, 2020, Making rose diagrams fit-for-purpose. _Earth-Science Reviews_ 201, 103055. [https://doi.org/10.1016/j.earscirev.2019.103055]
