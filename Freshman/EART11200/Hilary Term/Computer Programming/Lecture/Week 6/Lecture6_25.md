---
title: "Lecture6_25"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Lecture/Week 6/Lecture6_25.pdf"
type: pdf
---

<!-- Start of picture text -->
pandas and data discovery<br><!-- End of picture text -->

geospatial data practical 6

###### 'Vanilla' Python

Data types Loops Basic operations Conditionals **~~1 2~~**

# course layout

**~~3 4 5~~**

The Numpy Conway's Game Differential module Of Life Equations

Modules and Functions

###### Pandas and data discovery

Geospatial analysis

Statistical Cluster Analysis Analysis

**~~6 7 8 9~~**

<!-- Start of picture text -->
Creating a notebook assessment<br>select topic from weeks 4 - 9<br>10 11 12<br><!-- End of picture text -->

lecture + practical. Solutions are given

## recap

- Python comes in a few �avours. As we move away from Vanilla Python, we start using modules

- that offer a number of bene�ts: Quicker operations, better sharing...

- We can store information in arrays. These can be 1D, 2D, 3D, 4D. Indexing starts at 0.

- Functions help us repeat a set of operations many times

- We can create and use numerical models.

   - These can be built using existing 'solvers'

   - Traditional numerical models are built on differential equations

What if we have data we want to load in?

Data data everywhere...

## Data data everywhere...

Doing Data Science, O'Reilly ISBN: 978-1-44935865-5. ↑ Forbes-Gil PressA Very Short History of Data Science-May 2013

## in walks pandas

"pandas...provides high-performance, easy-touse data structures and data analysis tools.."

file formats can vary  e.g. JSOn file

## file formats can vary  e.g. netcdf A NetCDF file has dimensions, variables, and attributes.

## in walks pandas

"A Pandas DataFrame is twodimensional size-mutable, potentially heterogeneous tabular data structure with labeled axes (rows and columns). A Data frame is a twodimensional data structure, i.e., data is aligned in a tabular fashion in rows and columns. "

## in walks pandas

Access Pandas functions using the ‘.’ operator Access dataframe functions/proper ties using the ‘.’ operator

#### interrogating properties of the dataframe

##### e.g size and shape

interrogating properties of a column e.g size and shape

#### interrogating properties of a column e.g. unique entries

## extract values from a column

#### ENGLISH

We have a dataframe called 'data' We have a column labelled 'Start Year' We want to extract values from this column into a numpy array We want to �nd the minimum value in this array

#### python

## extract values from a column

#### ENGLISH

We have a dataframe called 'data' We have columns labelled 'Latitude' and 'Longitude' We want to extract values from this column into a numpy array

#### python

## extract a subset - using conditionals!

###### e.g preview only those entries where 'Start Year' == 2019

Notice the use of square brackets [  ] and the conditional within them

## extract a subset - using conditionals!

e.g extract lat-long coordinates between +/- 40 degrees

Notice the use of square brackets [ ] and the conditional within them Now we combine two conditional statements

<!-- Start of picture text -->
pandas and data discovery<br><!-- End of picture text -->

data data everywhere....in walks pandas

practical 6

## What can we do with geospatial data?

## What can we do with geospatial data?

load CSV file

Extract coordinates Plot of eruptions

It combines with Matplotlib and we provide you with the template for these plots. you do not need to remember these

### We can plot a subset of data!

Does the subset selection method make sense?

<!-- Start of picture text -->
pandas and data discovery<br><!-- End of picture text -->

data data everywhere....in walks pandas

geospatial data

<!-- Start of picture text -->
Lecture 6                                                  summary<br><!-- End of picture text -->

### interacting with data in python

- Data is everywhere.

- Pandas is a powerful module

- Pandas has internal functions and plotting capability

- We need to select data according to speci�c criteria - Pandas can do this for us

### geospatial plotting

- Cartopy module allows us to plot data with coordinates

<!-- Start of picture text -->
practical 6                                               goals<br><!-- End of picture text -->

### code

- Become familiar with the Pandas package

- Select a subset of data according to some criteria being met

- Generate histograms

### general experience

- Start to develop skills to interact with data - highly valuable

- Increase the diversity of problems you can solve
