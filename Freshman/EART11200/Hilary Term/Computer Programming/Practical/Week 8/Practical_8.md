---
title: "Practical_8"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Practical/Week 8/Practical_8.ipynb"
type: notebook
---

# Practical 8 - Pandas and statistics

<div class="alert alert-block alert-success">
<b>Objectives:</b> In this notebook we are going to use Pandas to load a spreadsheet of time series data and perform some statistical analysis on it. The data for this exercise has been taken from the following repository:

 - The Harvard Dataverse: https://dataverse.harvard.edu
 - Wang, Hongwei, 2019, "Air pollution and meteorological data in Beijing 2017-2018", https://doi.org/10.7910/DVN/USXCAK, Harvard Dataverse, V1
 - URL: https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/USXCAK

We are going to load two datasets: One with meterorological data, and the other with air quality data. It is important to understand the concentrations and variability of key pollutants as a function of time and meteorological conditions. We will do this through the following activities:

 - 1) [Using Pandas to createg a dataframe](#Part1)
      * [Exercise 1: Count how many meteorological stations there are in Beijing](#Exercise1)
      * [Exercise 2: Plot a histogram of temperature at the Shunyi meteorological station](#Exercise2)
 - 2) [Merging two dataframes: Using a common time index](#Part2)
      * [Exercise 3: Plot diurnal profile of PM2.5 for different months](#Exercise3)
      * [Exercise 4: Create a new dataframe for the air quality station 'pingchang'](#Exercise4)
 - 3) [Statistical analysis on dataframes¶](#Part3)
      * [Exercise 5: Create a heatmap of correlation coefficients for the air quality station 'pingchang'](#Exercise5)

As with our other notebooks, we will provide you with a template for plotting the results. Also please note that you should not feel pressured to complete every exercise in class. These practicals are designed for you to take outside of class and continue working on them. Proposed solutions to all exercises can be found in the 'Solutions' folder.
</div>

```python
if 'google.colab' in str(get_ipython()):
    from google.colab import drive
    mount='/content/gdrive'
    print("Colab: mounting Google drive on ", mount)
    drive.mount(mount)
    drive_root = mount + "/My Drive/Colab Notebooks/DEES_first_year/DEES_programming_course"
    # Change to the directories to get data files
    print("\nColab: Changing directory to ", drive_root)
    %cd $drive_root
else:
    print('Not running on CoLab')
```

### Using Pandas to open a CSV file and understanding a dataframe <a name="Part1"></a>

First let us load our dataset into a Pandas dataframe. If you remember from our last practical, we can use the internal Pandas function

```python
pd.read_csv(name of CSV file)
```

and then preview our dataframe using the

```python
<<name of dataframe>>.head()
```
function. We do this below by loading in a CSV file that gives us a range of meteorological variables from stations across Beijing over the years 2017 to 2018. Im giving my dataframe a name that at least reminds us it includes meteorological data. Thus Im using <code> data_meteo </code>.

```python
import pandas as pd
import os
from os import path

path=os.getcwd()
# Read data from file 'beijing_17_18_meo.csv'
# (in the same directory that your python process is based) You can control delimiters, rows, column names with read_csv (see later)

data_meteo = pd.read_csv(path+"/data/beijing_17_18_meo.csv")
data_meteo.head()

# Preview the first 5 lines of the loaded data
data_meteo.head()
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>station_id</th>
      <th>longitude</th>
      <th>latitude</th>
      <th>utc_time</th>
      <th>temperature</th>
      <th>pressure</th>
      <th>humidity</th>
      <th>wind_direction</th>
      <th>wind_speed</th>
      <th>weather</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>30/01/2017 16:00</td>
      <td>-1.7</td>
      <td>1028.7</td>
      <td>15</td>
      <td>215.0</td>
      <td>1.6</td>
      <td>Sunny/clear</td>
    </tr>
    <tr>
      <th>1</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>30/01/2017 17:00</td>
      <td>-3.5</td>
      <td>1028.4</td>
      <td>24</td>
      <td>16.0</td>
      <td>1.0</td>
      <td>Haze</td>
    </tr>
    <tr>
      <th>2</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>30/01/2017 18:00</td>
      <td>-3.7</td>
      <td>1028.1</td>
      <td>27</td>
      <td>32.0</td>
      <td>1.1</td>
      <td>Haze</td>
    </tr>
    <tr>
      <th>3</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>30/01/2017 19:00</td>
      <td>-3.9</td>
      <td>1027.6</td>
      <td>27</td>
      <td>21.0</td>
      <td>0.9</td>
      <td>Haze</td>
    </tr>
    <tr>
      <th>4</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>30/01/2017 20:00</td>
      <td>-4.1</td>
      <td>1026.7</td>
      <td>26</td>
      <td>17.0</td>
      <td>1.1</td>
      <td>Haze</td>
    </tr>
  </tbody>
</table>
</div>

I can also check the data type of each column by using the

```python
<<name of dataframe>>.dtypes
```
function. This is useful for a number of reasons that might include whether we need to convert between, for example, <code> string </code> to <code> float </code> to perform some numerical analysis. As we will see shortly, we can also check whether we are using a format called <code> datetime </code>. As the name suggests, this format allows us to perform some really neat data manipulation on time series data.  In the code box below, I check the data types of columns stored in our meteorology dataframe using the <code> .dtypes </code> property of our dataframe.

```python
data_meteo.dtypes
```

    station_id         object
    longitude         float64
    latitude          float64
    utc_time           object
    temperature       float64
    pressure          float64
    humidity            int64
    wind_direction    float64
    wind_speed        float64
    weather            object
    dtype: object

As per the last practical, let's see how many rows we have. This isnt always the best way to calculate the number of unique entries as duplicate datapoints can be common, but now that we have created a dataframe we can see how many entries it has. We can do this via the following properties of our frame:

```python
data.size
data.shape
data.ndim
```

```python
# Lets also check the data frame size
size = data_meteo.size
print("Size of dataframe =", size)

# dataframe.shape - gives the seperated number of rows, columns, etc
shape = data_meteo.shape
print("Shape of dataframe =", shape)

# dataframe.ndim  - Number of dimensions. Do we have a 2D array, 3D array?? etc
ndim = data_meteo.ndim
print("Number of dimensions =", ndim)
```

    Size of dataframe = 1580470
    Shape of dataframe = (158047, 10)
    Number of dimensions = 2

That is quite a large number of observations! Let's see how many unique stations there are in our first exercise. For this you might want to go back to Practical 6 and copy-and-paste code over, before changing portions of text for use here.

<div class="alert alert-block alert-success">
<b> Exercise 1: Count how many meteorological stations there are in Beijing. <a name="Exercise1"></a>  </b>

If you recall, in Practical 6, we were able to count how many unique values we had from a particular column in our data frame. In this case, you should find there are 18 different stations.

</div>

```python
#------'INSERT CODE HERE'------
data_meteo['station_id'].value_counts().size
#------------------------------
```

    18

<div class="alert alert-block alert-success">
<b> Exercise 2: Plot a histogram of temperature at Shunyi <a name="Exercise2"></a>  </b>

As a quick follow-on exercise, plot a histogram of temperature from the station with the ID <code> shunyi_meo </code>. If you recall, in Practical 6 we were able to generate a histogram from a particular column in our data frame. Your result should look like the following figure:

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical7_example1.png?raw=true)

</div>

```python
# Plot the histogram with one line
#------'INSERT CODE HERE'------
data_meteo[data_meteo['station_id'] == 'shunyi_meo'].hist(column='temperature')
#------------------------------
```

    array([[<Axes: title={'center': 'temperature'}>]], dtype=object)

![png](output_11_1.png)

### Merging two dataframes: Using a common time index <a name="Part2"></a>

Quite often, we do not have all the data we need in one place. You can spend a long time trying to merge datasets and then perform analysis on it. In the following we are going to load two files into two seperate dataframes before merging into one. Once we have the data in one frame, we can perform some correlation analysis on it.

Let us recap what happens when we load a file into a dataframe.

When we load our data into a frame, Pandas indexes each row...so we can access the data from it. You can see this index given on the left hand side in a preview of the frame via <code> .head() </code>. The problem we have is that, for correlation analysis, we want to make sure all of our data points are on a common index. In this case, we want to make sure we have our measurements on a common time base. As always, there is a Python function for that.  If you notice, our previously loaded dataframe has a column with a date/time stamp labelled as <code> utc_time </code>. This means 'Coordinated Universal Time (UTC)'. If we make that column our dataframe index, and then merge two dataframes onto this common index, we are in business.

We have already loaded the meteorological data, but let us now load in the air quality data. Again, once we load this in we will preview our dataframe using the <code> .head() </code> function.

```python
# Lets load the second spreadsheet
# Read data from file 'beijing_17_18_aq.csv'
# (in the same directory that your python process is based) You can control delimiters, rows, column names with read_csv (see later)

data_aq = pd.read_csv(path+"/data/beijing_17_18_aq.csv")
data_aq.head()
# Preview the first 5 lines of the loaded data
data_aq.head()# Read data from file 'beijing_17_18_meo.csv'
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>stationId</th>
      <th>utc_time</th>
      <th>PM2.5</th>
      <th>PM10</th>
      <th>NO2</th>
      <th>CO</th>
      <th>O3</th>
      <th>SO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>aotizhongxin_aq</td>
      <td>01/01/2017 14:00</td>
      <td>453.0</td>
      <td>467.0</td>
      <td>156.0</td>
      <td>7.2</td>
      <td>3.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>aotizhongxin_aq</td>
      <td>01/01/2017 15:00</td>
      <td>417.0</td>
      <td>443.0</td>
      <td>143.0</td>
      <td>6.8</td>
      <td>2.0</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>aotizhongxin_aq</td>
      <td>01/01/2017 16:00</td>
      <td>395.0</td>
      <td>467.0</td>
      <td>141.0</td>
      <td>6.9</td>
      <td>3.0</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>aotizhongxin_aq</td>
      <td>01/01/2017 17:00</td>
      <td>420.0</td>
      <td>484.0</td>
      <td>139.0</td>
      <td>7.4</td>
      <td>3.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>aotizhongxin_aq</td>
      <td>01/01/2017 18:00</td>
      <td>453.0</td>
      <td>520.0</td>
      <td>157.0</td>
      <td>7.6</td>
      <td>4.0</td>
      <td>9.0</td>
    </tr>
  </tbody>
</table>
</div>

## Implementing the datetime format

As already noted, we have a column that has information on the time each observation was made. When we interrogate the original data type we are told the <code> utc_time </code> column has the type <code> object </code>. The details are not important here but essentially this is telling us that we have variable string lengths in an array here. We know however this provides us with date and time.

The provenance and details of the datetime format are [long and convoluted](https://docs.python.org/3/library/datetime.html), but the important thing to note here is that once we convert strings to the datetime format, we can ask Pandas to extract powerful information like hourly averages or diurnal profiles without having to get our hands dirty with Numpy or similar.

First we need to convert the current data type. We can use the internal Pandas function:

```python
pandas.to_datetime()
```
In the following two code boxes we convert the <code> utc_time </code> column in both dataframes to datetime and then print the new list of data types. You may find this takes a few seconds.

```python
data_aq['utc_time']=pd.to_datetime(data_aq['utc_time'],format='mixed')
data_aq.dtypes
```

    stationId            object
    utc_time     datetime64[ns]
    PM2.5               float64
    PM10                float64
    NO2                 float64
    CO                  float64
    O3                  float64
    SO2                 float64
    dtype: object

```python
data_meteo['utc_time']=pd.to_datetime(data_meteo['utc_time'],format='mixed')
data_meteo.dtypes
```

    station_id                object
    longitude                float64
    latitude                 float64
    utc_time          datetime64[ns]
    temperature              float64
    pressure                 float64
    humidity                   int64
    wind_direction           float64
    wind_speed               float64
    weather                   object
    dtype: object

Can you see the <code> datetime64[ns] </code> result? Now let us move on with merging dataframes. We will come back to this new format shortly.

In the data preview you can see we have a column with an identification of station name. The meteorological file includes the extension _meo whereas the air quality dataset includes the extension _aq.

Before we merge dataframes into one, let us focus on one station for now: The Shunyi station.

We have already been practicing extracting data from a specific column. If we want to extract data from a specific site, thus row, we can also ask Pandas to extract only rows that match this criteria in our data frame. In doing so we can create two new dataframes:

 - One that includes meteorology data
 - One that includes air quality data

Check out the code below. As in the previous practical, Im using a conditional statement within square brackets:

```python
new_dataframe = old_dataframe[old_dataframe[column] == some value]
```

Just to re-iterate an important point on use of the equals sign. When we are checking a value is true, we use two equal signs <code> == </code> rather than one <code> = </code> when assigning a value to a variable. In the code box below, we now create two seperate dataframes for the Shunyi met and air quality stations.

```python
# Lets create a seperate Meteorology based data frame
Shunyi_met_df = data_meteo[data_meteo["station_id"] == "shunyi_meo"]
# And now lets create a seperate Air Quality based data frame
Shunyi_aq_df = data_aq[data_aq["stationId"] == "shunyi_aq"]

#Lets just check we have the right data by printing the head information:
# Preview the first 5 lines of the loaded data
Shunyi_met_df.head()
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>station_id</th>
      <th>longitude</th>
      <th>latitude</th>
      <th>utc_time</th>
      <th>temperature</th>
      <th>pressure</th>
      <th>humidity</th>
      <th>wind_direction</th>
      <th>wind_speed</th>
      <th>weather</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>2017-01-30 16:00:00</td>
      <td>-1.7</td>
      <td>1028.7</td>
      <td>15</td>
      <td>215.0</td>
      <td>1.6</td>
      <td>Sunny/clear</td>
    </tr>
    <tr>
      <th>1</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>2017-01-30 17:00:00</td>
      <td>-3.5</td>
      <td>1028.4</td>
      <td>24</td>
      <td>16.0</td>
      <td>1.0</td>
      <td>Haze</td>
    </tr>
    <tr>
      <th>2</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>2017-01-30 18:00:00</td>
      <td>-3.7</td>
      <td>1028.1</td>
      <td>27</td>
      <td>32.0</td>
      <td>1.1</td>
      <td>Haze</td>
    </tr>
    <tr>
      <th>3</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>2017-01-30 19:00:00</td>
      <td>-3.9</td>
      <td>1027.6</td>
      <td>27</td>
      <td>21.0</td>
      <td>0.9</td>
      <td>Haze</td>
    </tr>
    <tr>
      <th>4</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>2017-01-30 20:00:00</td>
      <td>-4.1</td>
      <td>1026.7</td>
      <td>26</td>
      <td>17.0</td>
      <td>1.1</td>
      <td>Haze</td>
    </tr>
  </tbody>
</table>
</div>

```python
#Same for the air quality data
Shunyi_aq_df.head()
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>stationId</th>
      <th>utc_time</th>
      <th>PM2.5</th>
      <th>PM10</th>
      <th>NO2</th>
      <th>CO</th>
      <th>O3</th>
      <th>SO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>195492</th>
      <td>shunyi_aq</td>
      <td>2017-01-01 14:00:00</td>
      <td>386.0</td>
      <td>477.0</td>
      <td>116.0</td>
      <td>6.3</td>
      <td>4.0</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>195493</th>
      <td>shunyi_aq</td>
      <td>2017-01-01 15:00:00</td>
      <td>410.0</td>
      <td>476.0</td>
      <td>121.0</td>
      <td>6.3</td>
      <td>4.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>195494</th>
      <td>shunyi_aq</td>
      <td>2017-01-01 16:00:00</td>
      <td>418.0</td>
      <td>493.0</td>
      <td>118.0</td>
      <td>6.8</td>
      <td>4.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>195495</th>
      <td>shunyi_aq</td>
      <td>2017-01-01 17:00:00</td>
      <td>474.0</td>
      <td>532.0</td>
      <td>133.0</td>
      <td>7.9</td>
      <td>5.0</td>
      <td>11.0</td>
    </tr>
    <tr>
      <th>195496</th>
      <td>shunyi_aq</td>
      <td>2017-01-01 18:00:00</td>
      <td>449.0</td>
      <td>456.0</td>
      <td>137.0</td>
      <td>7.3</td>
      <td>4.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>

So, we now have two seperate dataframes.

We want to merge both and make sure data on have data at the same point in time. Can you see an issue we have with both of our dataframes? The time stamp does not start at the same point. Fortunately, there is another Pandas function that can do this for us. The function is

```python
.merge
```
We [.merge](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.merge.html) two dataframes using a common index. In this case we want to merge values based on the column 'utc_time'. We are going to create a new dataframe by merging both Shunyi_aq_df and Shunyi_met_df according the the index given in column 'utc_time'.

But, can you see something that might be a problem? Each data frame uses the row number as index so we also need to change this to 'utc_time'. Thus we have two operations to perform:

1. Set the **index** of both dataframes to be the same
2. Merge both dataframes into one using this new index.

For the first point, we can do that for each dataframe by using the command

```python
.set_index('utc_time')
```

So, for example, when we run the following command do you see the index has changed?:

```python
# Set the index of the meteorological dataframe to be UTC time
Shunyi_met_df.set_index('utc_time')
# What do you see below?
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>station_id</th>
      <th>longitude</th>
      <th>latitude</th>
      <th>temperature</th>
      <th>pressure</th>
      <th>humidity</th>
      <th>wind_direction</th>
      <th>wind_speed</th>
      <th>weather</th>
    </tr>
    <tr>
      <th>utc_time</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2017-01-30 16:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-1.7</td>
      <td>1028.7</td>
      <td>15</td>
      <td>215.0</td>
      <td>1.6</td>
      <td>Sunny/clear</td>
    </tr>
    <tr>
      <th>2017-01-30 17:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-3.5</td>
      <td>1028.4</td>
      <td>24</td>
      <td>16.0</td>
      <td>1.0</td>
      <td>Haze</td>
    </tr>
    <tr>
      <th>2017-01-30 18:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-3.7</td>
      <td>1028.1</td>
      <td>27</td>
      <td>32.0</td>
      <td>1.1</td>
      <td>Haze</td>
    </tr>
    <tr>
      <th>2017-01-30 19:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-3.9</td>
      <td>1027.6</td>
      <td>27</td>
      <td>21.0</td>
      <td>0.9</td>
      <td>Haze</td>
    </tr>
    <tr>
      <th>2017-01-30 20:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-4.1</td>
      <td>1026.7</td>
      <td>26</td>
      <td>17.0</td>
      <td>1.1</td>
      <td>Haze</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2018-01-31 11:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-0.1</td>
      <td>1023.9</td>
      <td>19</td>
      <td>266.0</td>
      <td>1.7</td>
      <td>Sunny/clear</td>
    </tr>
    <tr>
      <th>2018-01-31 12:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-3.1</td>
      <td>1024.1</td>
      <td>30</td>
      <td>276.0</td>
      <td>1.1</td>
      <td>Sunny/clear</td>
    </tr>
    <tr>
      <th>2018-01-31 13:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-4.5</td>
      <td>1024.4</td>
      <td>39</td>
      <td>999017.0</td>
      <td>0.2</td>
      <td>Sunny/clear</td>
    </tr>
    <tr>
      <th>2018-01-31 14:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-4.3</td>
      <td>1024.5</td>
      <td>41</td>
      <td>37.0</td>
      <td>0.4</td>
      <td>Sunny/clear</td>
    </tr>
    <tr>
      <th>2018-01-31 15:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-6.0</td>
      <td>1024.4</td>
      <td>42</td>
      <td>324.0</td>
      <td>0.3</td>
      <td>Sunny/clear</td>
    </tr>
  </tbody>
</table>
<p>8781 rows × 9 columns</p>
</div>

Likewise, what happens when we set the air quality data frame index to 'utc_time'?

```python
# Now do the same for the other dataframe
Shunyi_aq_df.set_index('utc_time')
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>stationId</th>
      <th>PM2.5</th>
      <th>PM10</th>
      <th>NO2</th>
      <th>CO</th>
      <th>O3</th>
      <th>SO2</th>
    </tr>
    <tr>
      <th>utc_time</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2017-01-01 14:00:00</th>
      <td>shunyi_aq</td>
      <td>386.0</td>
      <td>477.0</td>
      <td>116.0</td>
      <td>6.3</td>
      <td>4.0</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>2017-01-01 15:00:00</th>
      <td>shunyi_aq</td>
      <td>410.0</td>
      <td>476.0</td>
      <td>121.0</td>
      <td>6.3</td>
      <td>4.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>2017-01-01 16:00:00</th>
      <td>shunyi_aq</td>
      <td>418.0</td>
      <td>493.0</td>
      <td>118.0</td>
      <td>6.8</td>
      <td>4.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>2017-01-01 17:00:00</th>
      <td>shunyi_aq</td>
      <td>474.0</td>
      <td>532.0</td>
      <td>133.0</td>
      <td>7.9</td>
      <td>5.0</td>
      <td>11.0</td>
    </tr>
    <tr>
      <th>2017-01-01 18:00:00</th>
      <td>shunyi_aq</td>
      <td>449.0</td>
      <td>456.0</td>
      <td>137.0</td>
      <td>7.3</td>
      <td>4.0</td>
      <td>11.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2018-01-31 11:00:00</th>
      <td>shunyi_aq</td>
      <td>30.0</td>
      <td>88.0</td>
      <td>45.0</td>
      <td>0.8</td>
      <td>37.0</td>
      <td>13.0</td>
    </tr>
    <tr>
      <th>2018-01-31 12:00:00</th>
      <td>shunyi_aq</td>
      <td>31.0</td>
      <td>88.0</td>
      <td>71.0</td>
      <td>0.9</td>
      <td>13.0</td>
      <td>16.0</td>
    </tr>
    <tr>
      <th>2018-01-31 13:00:00</th>
      <td>shunyi_aq</td>
      <td>36.0</td>
      <td>92.0</td>
      <td>79.0</td>
      <td>1.0</td>
      <td>6.0</td>
      <td>19.0</td>
    </tr>
    <tr>
      <th>2018-01-31 14:00:00</th>
      <td>shunyi_aq</td>
      <td>45.0</td>
      <td>103.0</td>
      <td>90.0</td>
      <td>1.4</td>
      <td>5.0</td>
      <td>18.0</td>
    </tr>
    <tr>
      <th>2018-01-31 15:00:00</th>
      <td>shunyi_aq</td>
      <td>44.0</td>
      <td>100.0</td>
      <td>90.0</td>
      <td>1.3</td>
      <td>5.0</td>
      <td>19.0</td>
    </tr>
  </tbody>
</table>
<p>8886 rows × 7 columns</p>
</div>

So each dataframe now uses the same index. We can now combine them into a new dataframe using the following function:

```python
pd.merge(dataframe1,dataframe2)
```

Please check the code snippet below. When this prints to the screen, you can see that our data now starts on the 30/1/2017, even though we had meteorological data before that date.

```python
# Now we can combine these into a new dataframe

combined_df=pd.merge(Shunyi_met_df,Shunyi_aq_df) #, how='inner',left_index=True, right_index=True)
combined_df.head()
combined_df=combined_df.set_index('utc_time')
combined_df.index
```

    DatetimeIndex(['2017-01-30 16:00:00', '2017-01-30 17:00:00',
                   '2017-01-30 18:00:00', '2017-01-30 19:00:00',
                   '2017-01-30 20:00:00', '2017-01-30 21:00:00',
                   '2017-01-30 22:00:00', '2017-01-30 23:00:00',
                   '2017-01-31 00:00:00', '2017-01-31 01:00:00',
                   ...
                   '2018-01-31 06:00:00', '2018-01-31 07:00:00',
                   '2018-01-31 08:00:00', '2018-01-31 09:00:00',
                   '2018-01-31 10:00:00', '2018-01-31 11:00:00',
                   '2018-01-31 12:00:00', '2018-01-31 13:00:00',
                   '2018-01-31 14:00:00', '2018-01-31 15:00:00'],
                  dtype='datetime64[ns]', name='utc_time', length=8220, freq=None)

```python
# Let's preview the new dataframe. Have the two previous frames merged? What difference can you notice,
# baring in mind that our start times were different? Pandas has sorted this out for us.
combined_df.head()
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>station_id</th>
      <th>longitude</th>
      <th>latitude</th>
      <th>temperature</th>
      <th>pressure</th>
      <th>humidity</th>
      <th>wind_direction</th>
      <th>wind_speed</th>
      <th>weather</th>
      <th>stationId</th>
      <th>PM2.5</th>
      <th>PM10</th>
      <th>NO2</th>
      <th>CO</th>
      <th>O3</th>
      <th>SO2</th>
    </tr>
    <tr>
      <th>utc_time</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2017-01-30 16:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-1.7</td>
      <td>1028.7</td>
      <td>15</td>
      <td>215.0</td>
      <td>1.6</td>
      <td>Sunny/clear</td>
      <td>shunyi_aq</td>
      <td>94.0</td>
      <td>104.0</td>
      <td>42.0</td>
      <td>0.2</td>
      <td>44.0</td>
      <td>27.0</td>
    </tr>
    <tr>
      <th>2017-01-30 17:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-3.5</td>
      <td>1028.4</td>
      <td>24</td>
      <td>16.0</td>
      <td>1.0</td>
      <td>Haze</td>
      <td>shunyi_aq</td>
      <td>136.0</td>
      <td>NaN</td>
      <td>52.0</td>
      <td>3.1</td>
      <td>28.0</td>
      <td>37.0</td>
    </tr>
    <tr>
      <th>2017-01-30 18:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-3.7</td>
      <td>1028.1</td>
      <td>27</td>
      <td>32.0</td>
      <td>1.1</td>
      <td>Haze</td>
      <td>shunyi_aq</td>
      <td>112.0</td>
      <td>NaN</td>
      <td>43.0</td>
      <td>2.5</td>
      <td>31.0</td>
      <td>26.0</td>
    </tr>
    <tr>
      <th>2017-01-30 19:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-3.9</td>
      <td>1027.6</td>
      <td>27</td>
      <td>21.0</td>
      <td>0.9</td>
      <td>Haze</td>
      <td>shunyi_aq</td>
      <td>110.0</td>
      <td>NaN</td>
      <td>42.0</td>
      <td>2.7</td>
      <td>26.0</td>
      <td>26.0</td>
    </tr>
    <tr>
      <th>2017-01-30 20:00:00</th>
      <td>shunyi_meo</td>
      <td>116.615278</td>
      <td>40.126667</td>
      <td>-4.1</td>
      <td>1026.7</td>
      <td>26</td>
      <td>17.0</td>
      <td>1.1</td>
      <td>Haze</td>
      <td>shunyi_aq</td>
      <td>112.0</td>
      <td>NaN</td>
      <td>43.0</td>
      <td>2.9</td>
      <td>NaN</td>
      <td>27.0</td>
    </tr>
  </tbody>
</table>
</div>

<div class="alert alert-block alert-success">
<b> Exercise 3: Plot diurnal profile of PM2.5 for different months <a name="Exercise3"></a>  </b>

Now that you have a new dataframe with a datetime index, we can plot diurnal profiles of entire columns with only one line of code! Specifically, we are going to use another plotting module called Seaborn to produce box-plots of, initially, PM2.5. In the code box below we provide you with a ready-made solution that looks at all of our data. The boxplot function of Seaborn requires that we specific the data we want to work with along with both the <code> x </code> and <code> y </code> variables as columns in that data. We have already defined a new data frame we want to work with, but how do we specific hours of day for our <code> x </code> variables? Take a look at the following code:

```python
import seaborn as sns
import matplotlib.pyplot as plt
fig, axes = plt.subplots(figsize=(8,8))
sns.boxplot(data=combined_df,x=combined_df.index.hour, y=combined_df['PM2.5'], ax=axes)
```
Remember that we can access properties of our dataframe using the <code> . </code> operator? Now that we have specified the index to be in the datetime format, we can access the <code> .index </code> of our dataframe and then the <code> .hour </code> of that index. Behind the scenes, Pandas can pass the data for our <code> y </code> variable of interest, <code> combined_df['PM2.5'] </code>, to the Seaborn box-plotting function.

Your challenge is to populate the right-hand plot, which is currently empty, with data on PM2.5 for August. Do you recall how we select data from our dataframe using conditional statements? As a clue, if I wanted to specify the month of March in a conditional statement I would write:

```python
combined_df.index.month == 3
```

</div>

</div>

```python
# Let's preview the new dataframe. Have the two previous frames merged? What difference can you notice,
# baring in mind that our start times were different? Pandas has sorted this out for us.
#combined_df.head()
import seaborn as sns
import matplotlib.pyplot as plt

#------'INSERT CODE HERE'------
fig, axes = plt.subplots(1,2,figsize=(12,8))
sns.boxplot(data=combined_df,x=combined_df.index.hour, y=combined_df['PM2.5'], ax=axes[0]).set(xlabel='Hour of day',ylabel='Abundance')
sns.boxplot(data=combined_df[combined_df.index.month == 8],x=combined_df[combined_df.index.month == 8].index.hour, y=combined_df[combined_df.index.month == 8]['PM2.5'], ax=axes[1]).set(xlabel='Hour of day',ylabel='Abundance')
axes[0].set_ylim([0,100])
axes[1].set_ylim([0,100])
axes[0].set_title('All year')
axes[1].set_title('August')
#------------------------------

```

    Text(0.5, 1.0, 'August')

![png](output_28_1.png)

<div class="alert alert-block alert-success">
<b> Exercise 4: Create a new dataframe for the air quality station 'pingchang' <a name="Exercise4"></a>  </b>

In this exercise you will need to combine the operations above and merge the meteorology and air quality existing datasets into a new one for the station Pingchang. Once you have done that, access a preview:

![](images/Practical7_preview_output.png )

and also calculate the maximum and minimum of each air quality variable using the relevant Numpy functions. Your results should confirm:

 - PM2.5 = 522.0
 - PM10 = 1010.0
 - NO2 = 154.0
 - CO = 6.4
 - O3 = 378.0
 - SO2 = 300.0

Following this, produce a diurnal plot for PM2.5 and PM10 side-by-side. You may find you need to change the scales of each graph to make for easier comparison.

<div class="alert alert-block alert-warning">
<b>Please note:</b> If the results from your maximum calculation all produce a 'Nan' (Not-a-number), this means your columns have NaN values. In this case, let us assume you do not want to investigate those but simply ignore them. In this case you can use

```python
numpy.nanmax
```

</div>

</div>

```python
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

#------'INSERT CODE HERE'------
# Lets create a seperate Meteorology based data frame
pingchang_met_df = data_meteo[data_meteo["station_id"] == "pingchang_meo"]
# And now lets create a seperate Air Quality based data frame
pingchang_aq_df = data_aq[data_aq["stationId"] == "pingchang_aq"]

# Set the index of the meteorological dataframe to be UTC time
pingchang_met_df.set_index('utc_time')
# Now do the same for the other dataframe
pingchang_aq_df.set_index('utc_time')

#combined_df_new=pd.merge(pingchang_met_df,pingchang_aq_df,on='utc_time')
combined_df_new=pd.merge(pingchang_met_df,pingchang_aq_df) #, how='inner',left_index=True, right_index=True)
combined_df_new.head()
combined_df_new=combined_df_new.set_index('utc_time')

combined_df_new.head()

PM25 = np.nanmax(combined_df_new["PM2.5"].values)
PM10 = np.nanmax(combined_df_new["PM10"].values)
NO2 = np.nanmax(combined_df_new["NO2"].values)
CO = np.nanmax(combined_df_new["CO"].values)
O3 = np.nanmax(combined_df_new["O3"].values)
SO2 = np.nanmax(combined_df_new["SO2"].values)

print("Max value for PM2.5 = ",PM25)
print("Max value for PM10 = ",PM10)
print("Max value for NO2 = ",NO2)
print("Max value for CO = ",CO)
print("Max value for O3 = ",O3)
print("Max value for SO2 = ",SO2)

fig, axes = plt.subplots(1,2,figsize=(12,8))
sns.boxplot(data=combined_df,x=combined_df_new.index.hour, y=combined_df_new['PM2.5'], ax=axes[0]).set(xlabel='Hour of day',ylabel='Abundance')
sns.boxplot(data=combined_df,x=combined_df_new.index.hour, y=combined_df_new['PM10'], ax=axes[1]).set(xlabel='Hour of day',ylabel='Abundance')
axes[0].set_ylim([0,100])
axes[1].set_ylim([0,200])
axes[0].set_title('PM2.5')
axes[1].set_title('PM10')
#------------------------------

```

    Max value for PM2.5 =  522.0
    Max value for PM10 =  1010.0
    Max value for NO2 =  154.0
    Max value for CO =  6.4
    Max value for O3 =  378.0
    Max value for SO2 =  300.0

    Text(0.5, 1.0, 'PM10')

![png](output_30_2.png)

### Statistical analysis on dataframes <a name="Part3"></a>

We have gone to all this trouble to build dataframes. We have practiced selecting a subset and also merging to create a new frame. We can also now perform common statistical operations on our data to try and understand any interesting relationships across multiple variables.

### Correlation coefficients

Pandas has a variety of functions for generating stats from our data. In the following code I demonstrate how we can select a subset of our columns and look at the correlation coefficient between each variable. Let us work with our new combined dataframe 'combined_df'.

The first step is to create a correlation coefficient matrix. We can do that by telling Pandas which columns we are interested in:

```python
dataframe[['column 1','column 2','column 3'...etc]]
```

and then using the

```python
.corr()
```

to this subset:

```python
corr = combined_df[['temperature','pressure','humidity','PM2.5','PM10','NO2','CO','O3','SO2']].corr()
print("Correlation coefficient matrix = ", corr)
```

    Correlation coefficient matrix =               temperature  pressure  humidity     PM2.5      PM10       NO2  \
    temperature     1.000000 -0.862873  0.213701  0.041147  0.184763 -0.182444
    pressure       -0.862873  1.000000 -0.276145 -0.086732 -0.235992  0.039646
    humidity        0.213701 -0.276145  1.000000  0.293561  0.093653  0.251402
    PM2.5           0.041147 -0.086732  0.293561  1.000000  0.844545  0.513936
    PM10            0.184763 -0.235992  0.093653  0.844545  1.000000  0.359391
    NO2            -0.182444  0.039646  0.251402  0.513936  0.359391  1.000000
    CO             -0.201598  0.083819  0.264412  0.761744  0.557353  0.593860
    O3              0.578449 -0.459206 -0.266630 -0.066553  0.026601 -0.521188
    SO2            -0.254369  0.189250 -0.144239  0.490951  0.249974  0.443254

                       CO        O3       SO2
    temperature -0.201598  0.578449 -0.254369
    pressure     0.083819 -0.459206  0.189250
    humidity     0.264412 -0.266630 -0.144239
    PM2.5        0.761744 -0.066553  0.490951
    PM10         0.557353  0.026601  0.249974
    NO2          0.593860 -0.521188  0.443254
    CO           1.000000 -0.242110  0.572908
    O3          -0.242110  1.000000 -0.127776
    SO2          0.572908 -0.127776  1.000000

So here we have our correlation coefficients! It would be much easier to visualise this somehow. A popular plotting module used with Pandas is [Seaborn](https://seaborn.pydata.org):

>>> Seaborn is a Python data visualization library based on matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics.

Check out the code snippet below:

```python
import matplotlib.pyplot as plt
import seaborn as sns
# calculate the correlation matrix
corr = combined_df[['temperature','pressure','humidity','wind_direction','wind_speed','PM2.5','PM10','NO2','CO','O3','SO2']].corr()
# Now use an internal function within Seaborn called '.heatmap'
sns.heatmap(corr, xticklabels=corr.columns, yticklabels=corr.columns)
# And we now need to show the plot.
plt.show()
```

![png](output_34_0.png)

<div class="alert alert-block alert-success">
<b> Exercise 5: Create a heatmap of correlation coefficients for the air quality station 'pingchang' <a name="Exercise5"></a>  </b>

Replicate the procedures given above for your new merged dataframe created in Exercise 4. Your heatmap should look like the following figure:

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical7_heatmap_output.png?raw=true)

</div>

```python
import matplotlib.pyplot as plt
import seaborn as sns
# calculate the correlation matrix

#------'INSERT CODE HERE'------
corr_new = combined_df_new[['temperature','pressure','humidity','wind_direction','wind_speed','PM2.5','PM10','NO2','CO','O3','SO2']].corr()
# Now use an internal function within Seaborn called '.heatmap'
sns.heatmap(corr_new, xticklabels=corr_new.columns, yticklabels=corr_new.columns)
#------------------------------

# And we now need to show the plot.
plt.show()
```

![png](output_36_0.png)

We can even try to viualise all of these relationships via a series of scatter plots. To make this easier to visualise let's focus on 9 variables and also apply the <code> .dropna() </code> extension to our dataframe to remove <code> NaN </code> entries. An entry of <code> NaN </code> can often arise through errors in processing and literally means 'Not-a-Number'.

```python
# Create the default pairplot
sns.pairplot(combined_df[['temperature','pressure','humidity','PM2.5','PM10','NO2','CO','O3','SO2']].dropna())
```

    /Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/seaborn/_oldcore.py:1119: FutureWarning: use_inf_as_na option is deprecated and will be removed in a future version. Convert inf values to NaN before operating instead.
      with pd.option_context('mode.use_inf_as_na', True):
    /Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/seaborn/_oldcore.py:1119: FutureWarning: use_inf_as_na option is deprecated and will be removed in a future version. Convert inf values to NaN before operating instead.
      with pd.option_context('mode.use_inf_as_na', True):
    /Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/seaborn/_oldcore.py:1119: FutureWarning: use_inf_as_na option is deprecated and will be removed in a future version. Convert inf values to NaN before operating instead.
      with pd.option_context('mode.use_inf_as_na', True):
    /Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/seaborn/_oldcore.py:1119: FutureWarning: use_inf_as_na option is deprecated and will be removed in a future version. Convert inf values to NaN before operating instead.
      with pd.option_context('mode.use_inf_as_na', True):
    /Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/seaborn/_oldcore.py:1119: FutureWarning: use_inf_as_na option is deprecated and will be removed in a future version. Convert inf values to NaN before operating instead.
      with pd.option_context('mode.use_inf_as_na', True):
    /Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/seaborn/_oldcore.py:1119: FutureWarning: use_inf_as_na option is deprecated and will be removed in a future version. Convert inf values to NaN before operating instead.
      with pd.option_context('mode.use_inf_as_na', True):
    /Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/seaborn/_oldcore.py:1119: FutureWarning: use_inf_as_na option is deprecated and will be removed in a future version. Convert inf values to NaN before operating instead.
      with pd.option_context('mode.use_inf_as_na', True):
    /Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/seaborn/_oldcore.py:1119: FutureWarning: use_inf_as_na option is deprecated and will be removed in a future version. Convert inf values to NaN before operating instead.
      with pd.option_context('mode.use_inf_as_na', True):
    /Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/seaborn/_oldcore.py:1119: FutureWarning: use_inf_as_na option is deprecated and will be removed in a future version. Convert inf values to NaN before operating instead.
      with pd.option_context('mode.use_inf_as_na', True):

    <seaborn.axisgrid.PairGrid at 0x1693c3170>

![png](output_39_2.png)

### Additional example: Producing a box-plot of our dataframe

In addition to correlation coefficients, we can get a better understanding of our data through a series of box-plots. A box-plot. A [very nice overview]() is:

> Boxplots are a standardized way of displaying the distribution of data based on a five number summary (“minimum”, first quartile (Q1), median, third quartile (Q3), and “maximum”).

> - median (Q2/50th Percentile): the middle value of the dataset.
> - first quartile (Q1/25th Percentile): the middle number between the smallest number (not the “minimum”) and the median of the dataset.
> - third quartile (Q3/75th Percentile): the middle value between the median and the highest value (not the “maximum”) of the dataset.
> - interquartile range (IQR): 25th to the 75th percentile.
> - whiskers
> - outliers
> - “maximum”: Q3 + 1.5*IQR
> - “minimum”: Q1 -1.5*IQR

As an example, lets see how the PM2.5 data varies in our new dataframe as:

```python
combined_df_new[['PM2.5','PM10','NO2','CO','O3','SO2']].boxplot(column=['PM2.5','PM10','NO2','CO','O3','SO2'])
```

    <Axes: >

![png](output_41_1.png)

Let us make the figure bigger and also use a Log scale for the y-axes:

```python
combined_df_new[['PM2.5','PM10','NO2','CO','O3','SO2']].boxplot(
    column=['PM2.5','PM10','NO2','CO','O3','SO2'],figsize=(12,12)).set_yscale('log')

```

![png](output_43_0.png)

## ⚙️ What We Did

> 🟦 **In this practical, we:**
>
> - Used **Pandas** to load time-series data from a spreadsheet
> - Worked with dates and time as part of a dataset
> - Explored the structure of the data to understand:
>   - What each column represents
>   - How values change over time
> - Used Pandas tools to calculate **basic statistical quantities**, including:
>   - Mean
>   - Minimum and maximum values
>   - Standard deviation
> - Applied these statistics to real data to summarise trends and variability
> - Created plots to visualise how values evolve through time
> - Began interpreting numerical summaries alongside graphical output
>
> 🧠 *The focus was on using statistics to describe real datasets, and understanding how numerical summaries and plots complement each other.*

---

## 📝 Exercises

> 🟦 **Exercise 1: Loading and inspecting time-series data**
>
> - Loaded a spreadsheet containing time-series measurements into Pandas
> - Inspected column names, data types, and overall structure
> - Checked that the data had loaded correctly before analysis
>
> 🧠 *Goal: build confidence loading and inspecting real-world datasets.*

---

> 🟦 **Exercise 2: Calculating basic statistics**
>
> - Calculated summary statistics such as:
>   - Mean values
>   - Minimum and maximum values
>   - Standard deviation
> - Compared statistical results across different columns
>
> 🧠 *Goal: understand what basic statistics tell us about a dataset.*

---

> 🟦 **Exercise 3: Visualising time-series data**
>
> - Created plots showing how values change over time
> - Compared multiple variables on the same timeline
> - Linked features in the plot to calculated statistics
>
> 🧠 *Goal: connect numerical summaries to visual trends.*

---

> 🟦 **Exercise 4: Interpreting variability**
>
> - Used statistical measures to identify:
>   - Periods of high variability
>   - More stable intervals
> - Considered what these patterns might mean in a real-world context
>
> 🧠 *Goal: move beyond calculation and start interpreting what the numbers tell us.*

```python

```
