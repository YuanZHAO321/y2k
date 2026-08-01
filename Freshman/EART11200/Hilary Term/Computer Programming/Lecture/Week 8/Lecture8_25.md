---
title: "Lecture8_25"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Lecture/Week 8/Lecture8_25.pdf"
type: pdf
---

<!-- Start of picture text -->
pandas and data discovery<br><!-- End of picture text -->

#### practical 8

##### 'Vanilla' Python

Data types Loops Basic operations Conditionals **~~1 2~~**

# course layout

**~~3 4 5~~**

The Numpy Conway's Game Differential module Of Life Equations

Modules and Functions

##### Pandas and data discovery

Geospatial analysis

Statistical Cluster Analysis Analysis

**~~6 7 8 9~~**

<!-- Start of picture text -->
Creating a notebook assessment<br>select topic from weeks 4 - 9<br>10 11 12<br><!-- End of picture text -->

lecture + practical. Solutions are given

## recap

- Pandas allows us to store information in a dataframe

- Pandas can deal with various data types

- We can access entries in that dataframe according to certain criteria

- Dataframes have internal functions we can use to our advantage

What if we have data we want to perform statistical analysis on the data?

## statistical visualisations can tell a story

## statistical visualisations can tell a story

#### What if we have data we want to perform statistical analysis on the data?

Setting the index of a dataframe - What is an index?

Merging two dataframes - Why do we want to do this? Performing statistical analysis - Understanding our data! > Correlation coe�cients > Pair plots > Box-plots

## what is an index?

Each column has a name associated with it, also known as a label. We can access entries in speci�c columns:

When you ask for a preview, Pandas will assign an integer index system. The index of a Dataframe is a set that consists of a label for each row

## setting an index - 1) merging dataframes

Quite often, we dont have all the data we need in one place. You can spend a long time trying to merge datasets into one place. Here we can use Pandas to merge to a common index.

Merge into one dataframe!

## setting an index - 1) merging dataframes

But...what has happened to the index of our new dataframe?

## setting an index - 2) accessing diurnal profiles

seaborn: statistical data visualization

## setting an index - 2) accessing diurnal profiles

x=combined_df.index.hour y=combined_df['PM2.5']

## statistical analysis

combined_df_new[['temperature','pressure','humidity','wind_direction','wind_speed','PM2.5','PM10','NO2','CO','O3','SO2']].corr()

## check out seaborn

<!-- Start of picture text -->
pandas and data discovery<br><!-- End of picture text -->

manipulating dataframes AND statistical analysis

practical 8

<!-- Start of picture text -->
Lecture 7                                                  summary<br><!-- End of picture text -->

### interacting with data in python

- Data is everywhere.

- Pandas is a powerful module

- We can merge time series data on a common period using simple Pandas functions

- We can extract seasonality/diurnal trends

- Statistical analysis

   - Combined with the Seaborn plotting module, we can visualise multiple statistics describing our data

-

<!-- Start of picture text -->
practical 7                                               goals<br><!-- End of picture text -->

### code

- Using Pandas to createg a dataframe

- Merge two dataframes using a common time index

- Perform statistical analysis on dataframes

### general experience

- Continue your journey with Pandas

- Start to discover relationships in a dataset
