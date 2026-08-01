---
title: "Practical_9"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Practical/Week 9/Practical_9.ipynb"
type: notebook
---

# Practical 9: Pandas to Machine learning

<div class="alert alert-block alert-success">
<b>Objectives:</b> In this practical we keep moving with applied demonstrations of modules you can use in Python. Today we continue to practice using Pandas, but also start applying some common machine learning techniques. Specifically, we will use Cluster Analysis [also known as unsupervised machine learning] to study distinct groupings on two very different datasets. We will also use a method to predict a label based on a number of features, or variables [also known as supervised machine learning]

We will work with two existing datasets in this notebook. These are:
- a dataset from the UC Irvine Machine Learning repository on forest fires. This dataset, saved as a <code> .csv </code> file, is taken from the study:[Cortez and Morais, 2007] P. Cortez and A. Morais. A Data Mining Approach to Predict Forest Fires using Meteorological Data. In J. Neves, M. F. Santos and J. Machado Eds., New Trends in Artificial Intelligence, Proceedings of the 13th EPIA 2007 - Portuguese Conference on Artificial Intelligence, December, Guimarães, Portugal, pp. 512-523, 2007. APPIA, ISBN-13 978-989-95618-0-9.*
- a dataset from the UC Irvine Machine Learning repository of acoustic features extracted from syllables of anuran (frogs) calls, including the family, the genus, and the species labels (multilabel): Colonna, J., Nakamura, E., Cristo, M., & Gordo, M. (2015). Anuran Calls (MFCCs) [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5CC9H.

The notebook is split according to the following activities.

 - [1) Introduction to Machine Learning](#Part1)
 - - [1.1)The Evolution of AI and the Rise of Foundational Models](#Part1.1)
 - - [1.2) Introduction to Unsupervised learning - Cluster Analysis](#Part1.2)

      * [Exercise 1: Plot a histogram of meteorological variables and fire extent](#sExercise1)
      * [Exercise 2: Produce a correlation coefficient matrix](#Exercise2)

 - - - [1.2.1) K-means cluster analysis](#Part1.2.1)
      * [Exercise 3: Create new dataframe with only positive values of fire area and repeat cluster analysis](#Exercise3)
 - - - [1.2.2) Scaling data prior to clustering - 'Standardising' ](#Part1.2.2)

 - - [1.3) Working with 'labelled' data](#Part1.3)
      * [Exercise 4a: Generate lists of unique entries in columns 'Family', 'Genus' and 'Species'](#Exercise4a)
      * [Exercise 4b: Generate a set of figures that highlight the distribution of individual features as a function of Family label.](#Exercise4b)
 - - [1.4) Dimension reduction](#Part1.4)
      * [Exercise 5: Apply Principal Component Analysis to the target label 'Genus'](#Exercise5)
 - - [1.5) Evaluating the accuracy of a clustering algorithm with 'labelled' data](#Part1.5)
      * [Exercise 6: Apply K-means to the target label 'Genus' with no dimension reduction](#Exercise6)

 - 2) [Introduction to Supervised Machine Learning](#Part2)
 - - [2.1) Train, test and validate](#Part2.1)
 - - [2.2) Predicting Labels from Features using Random Forests in scikit-learn](#Part2.2)
      * [Exercise 7: Evaluate the accuracy of a Random Forest Classifier in predicting the target label 'Species'](#Exercise7)

As with our other notebooks, we will provide you with a template for plotting the results. Also please note that you should not feel pressured to complete every exercise in class. These practicals are designed for you to take outside of class and continue working on them. Proposed solutions to all exercises can be found in the 'Solutions' folder.
</div>

<div class="alert alert-block alert-danger">
<b> Using Google Colabs </b> Please note that the first code block ensures that we can access our files IF we are running this example on Google Colab. Please run this code block and, if you are not on Google Colab, you will recieve a message that confirms this.
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

## 1) Introduction to Machine Learning <a name="Part1"></a>

Machine learning (ML) is a branch of artificial intelligence (AI) that enables computers to learn from data and make predictions or decisions without being explicitly programmed. There is an important nuance in this narrative; software engineers and scienctists are still required, but the ultimate aim is to enable automation. Unlike traditional programming, where a set of rules is hard-coded by humans, machine learning systems improve their performance by identifying patterns in data.  The best example from this course would be referring back to using Python to integrate differential equations. In that notebook you explicitly wrote down the equations to be solved.  What if we didnt know what the underlying theory was but we had data on the system we are interested in? This is one example where machine learning could be used and applied to the data to understand what underlying processes may be occuring. ML algorithms can broadly be categorized into supervised and unsupervised learning. In supervised learning, the algorithm learns from labeled data, meaning each input has a corresponding known output. This approach is commonly used for tasks such as image classification, spam detection, and predicting house prices. In contrast, unsupervised learning involves training algorithms on data without explicit labels. These algorithms identify hidden structures or patterns in the data, making it useful for tasks such as customer segmentation or anomaly detection. A [schematic](https://towardsdatascience.com/machine-learning-algorithms-in-laymans-terms-part-1-d0368d769a7b) on the different types of machine learning algorithms is provided in the figure below:

<div>
<img src="https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical_9_figure1.png?raw=true" width="600"/>
</div>

While all machine learning models aim to learn from data, they can be distinguished by the complexity of their architectures. Shallow learning models, such as linear regression, decision trees, and support vector machines, focus on relatively simple transformations of data and typically require more feature engineering from humans. On the other hand, deep learning refers to models that use neural networks with many layers to automatically learn hierarchical representations of data. These models are capable of handling vast amounts of unstructured data, such as images, audio, and text, and have driven breakthroughs in fields like computer vision, natural language processing, and robotics. There are a lot of approaches mentioned in the previous sentences. Do not worry about understanding what they mean since you are best placed to start learning about the wide range of approaches available according to your problem at hand. Indeed a course on manchine learning could fill a semester. For now, the key difference lies in the depth of the model and the level of abstraction it can achieve: shallow learning models are better suited for simpler tasks, while deep learning excels at capturing more complex patterns in large datasets. We will integrate a number of shallow models in this practical. The [figure](https://www.analyticsvidhya.com/blog/2022/12/machine-learning-with-limited-data/) below is a very nice visulisation of how choice of method, or algorithm, used depends on the amount of data you may have:

<div>
<img src="https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical_9_figure2.jpg?raw=true" width="600"/>
</div>

If you are interested in learning more about Deep Learning (DL), a number of references will be given during the course.

### 1.1) The Evolution of AI and the Rise of Foundational Models <a name="Part1.1"></a>
Artificial Intelligence (AI) has seen unprecedented advancements in recent years, largely driven by breakthroughs in machine learning techniques and the availability of vast amounts of data and computational power. Early AI systems were task-specific, relying on carefully designed rules to perform narrow functions such as playing chess or automating simple workflows. However, recent progress has led to the emergence of more generalized AI systems capable of performing a wide variety of tasks with minimal human intervention. A significant milestone in this evolution is the development of foundational models—large, versatile machine learning models that serve as a base for many AI applications across different domains.

Foundational models, such as large language models (e.g., GPT) and multimodal models (which process both text and images), are trained on massive datasets and can be fine-tuned for specific tasks with relatively small amounts of additional data. These models demonstrate an advanced capability to understand and generate human-like text, interpret images, and even engage in complex problem-solving. While they offer immense potential, foundational models also come with challenges, including the need for immense computational resources, concerns about bias, and ethical considerations. Their emergence marks a shift from traditional, task-specific AI systems toward more adaptable and scalable AI solutions that push the boundaries of what machine learning can achieve. Guess what, the Python ecosystem has adapted to this rapid pace such that we can even consider building our own foundational model if we had the right computer hardware. This is beyond the remit of this course, but we can still interact with any number of developments in this space, including LLMs, or Large Language Models, to which ChatGPT is the perfect example.

First lets start with some common applications of machine learning.

### 1.2) Introduction to Unsupervised learning - Cluster Analysis <a name="Part1.2"></a>

Machine learning is all the rage these days. One branch of machine learning are a family of algorithms known as unsupervised methods. These attempt to extract patterns from a dataset according to a number of assumptions. Cluster Analysis is a subset of such methods, and used across the sciences. An excellent overview of some of the challenges is given in the documentation of a method known as [HDBSCAN](https://hdbscan.readthedocs.io/en/latest/comparing_clustering_algorithms.html)

>> There are a lot of clustering algorithms to choose from. The standard sklearn clustering suite has thirteen different clustering classes alone. So what clustering algorithms should you be using? As with every question in data science and machine learning it depends on your data. A number of those thirteen classes in sklearn are specialised for certain tasks (such as co-clustering and bi-clustering, or clustering features instead data points). Obviously an algorithm specializing in text clustering is going to be the right choice for clustering text data, and other algorithms specialize in other specific kinds of data. Thus, if you know enough about your data, you can narrow down on the clustering algorithm that best suits that kind of data, or the sorts of important properties your data has, or the sorts of clustering you need done.

We are going to use the K-means method for our first example of clustering. K-means is perhaps one of the most simplest methods for clustering and, whilst fast, has limitations when dealing with complex datasets. Distance-based clustering is an unsupervised machine learning technique used to group similar data points into clusters based on their proximity in feature space. This is another way of defining similarity. Our brains start to learn similarity between objects from the day we are born. But what do we do with numbers? Basically we assume that numbers that are close together might belong to the same 'group'. These numbers can represent features; abstract ones or physical variables such as height, weight, poewr etc. The goal is to minimize the distance between points within the same cluster while maximizing the distance between points in different clusters. A common way to measure this distance is through metrics such as Euclidean distance. Distance-based clustering is useful for tasks like customer segmentation, image compression, and anomaly detection, where the structure or grouping in data isn’t immediately apparent.

If you are interested you can find some excellent tutorials and examples on the official [Scikit-learn webpage](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html)

<div>
<img src="https://github.com/loftytopping/DEES_programming_course/blob/master/images/sphx_glr_plot_kmeans_assumptions_001.png?raw=true" width="600"/>
</div>

Before we jump into using K-means, we need to try and understand our data as per the above discussion.

```python
import pandas as pd #Im using pd here as its easier to keep writing! You can use whatever you want, but it might help you to use 'pd' for now.
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
import seaborn as sns
import os
from os import path

path=os.getcwd()

# Read data from file
# We are going to use the function 'read_csv' within the Pandas package:

data = pd.read_csv(path+"/data/forestfires.csv")
data.head()

# Notice how we call that function using the '.' operator?
# (Note the data file needs to be in the same directory that your jupyter notebook is based) You can control delimiters, rows, column names with read_csv (see later)

# How do we preview the data file.
# Preview the first 5 lines of the loaded data
data.head()
#data.columns.values
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
      <th>X</th>
      <th>Y</th>
      <th>month</th>
      <th>day</th>
      <th>FFMC</th>
      <th>DMC</th>
      <th>DC</th>
      <th>ISI</th>
      <th>temp</th>
      <th>RH</th>
      <th>wind</th>
      <th>rain</th>
      <th>area</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7</td>
      <td>5</td>
      <td>mar</td>
      <td>fri</td>
      <td>86.2</td>
      <td>26.2</td>
      <td>94.3</td>
      <td>5.1</td>
      <td>8.2</td>
      <td>51</td>
      <td>6.7</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>7</td>
      <td>4</td>
      <td>oct</td>
      <td>tue</td>
      <td>90.6</td>
      <td>35.4</td>
      <td>669.1</td>
      <td>6.7</td>
      <td>18.0</td>
      <td>33</td>
      <td>0.9</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>7</td>
      <td>4</td>
      <td>oct</td>
      <td>sat</td>
      <td>90.6</td>
      <td>43.7</td>
      <td>686.9</td>
      <td>6.7</td>
      <td>14.6</td>
      <td>33</td>
      <td>1.3</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>8</td>
      <td>6</td>
      <td>mar</td>
      <td>fri</td>
      <td>91.7</td>
      <td>33.3</td>
      <td>77.5</td>
      <td>9.0</td>
      <td>8.3</td>
      <td>97</td>
      <td>4.0</td>
      <td>0.2</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8</td>
      <td>6</td>
      <td>mar</td>
      <td>sun</td>
      <td>89.3</td>
      <td>51.3</td>
      <td>102.2</td>
      <td>9.6</td>
      <td>11.4</td>
      <td>99</td>
      <td>1.8</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
</div>

<div class="alert alert-block alert-success">
<b> Exercise 1: Plot a histogram of meteorological variables and fire extent <a name="Exercise1"></a>  </b> The purpose of this exercise is to understand our dataset a little before we start to apply any cluster analysis. We will discuss the reason for this as we apply cluster analysis. For the meteorological variables you need to produce a histogram for:

 - 'temp': Temperature
 - 'RH' : Relative Humidity
 - 'wind': Wind speed
 - 'Rain': Rainfall

Rather than produce one 'big' plot for each I have provided you with the code for creating a tile of subplots. This looks like:

```python
# Import Matplotlib for plotting
import matplotlib.pyplot as plt

# This command assigns variables for the entire figure and axes that are distributed over the figure space according to the number of rows and columns in the parentheses. I also specify a figure size and tell Matplotlib I dont want each plot to share the same y-axes scale [sharey=False]
fig, axs = plt.subplots(2, 3, figsize=(12, 8), sharey=False)
# Create a histogram for the varible 'temp'. The command ax=axs[0,0] tells Matplotlib to focus on the axes 'ax' using the index assigned earlier.
data.hist(column='temp',ax=axs[0,0])
```

When you you have finished the code for the other variables, you figure should look like the following figure:

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical8_example.png?raw=true)

<div class="alert alert-block alert-warning">
<b>Please note:</b> For each histogram you will need to change the values within the command:

```python
ax=axs[0,0]
```
where the first value indicates the row, and the second the column value.

</div>

</div>

```python
# Make a boxplot for each column. We could group them into one figure but this is beyond the scope of this practical.
# In the template below I have given you a template to include a boxplot in each subplot
import matplotlib.pyplot as plt

fig, axs = plt.subplots(2, 3, figsize=(12, 8), sharey=False)
# Temperature
data.hist(column='temp',ax=axs[0,0])
#------'INSERT CODE HERE'------
# RH
data.hist(column='RH',ax=axs[0,1])
# Wind
data.hist(column='wind',ax=axs[0,2])
# Rain
data.hist(column='rain',ax=axs[1,0])
# Fire area
data.hist(column='area',ax=axs[1,1])
#------------------------------
```

    array([<matplotlib.axes._subplots.AxesSubplot object at 0x1a16d80390>],
          dtype=object)

![png](output_7_1.png)

For the first three variables, we can easily infer a distribution of values. For the final two variables, however, the distribution is much harder to interpret due to a very high number of small values. Given that we are interested in forest fires, we need to consider whether this might influence our clustering. Why is that? If we are using the values of each variable to calculate a 'distance' between each observation, a variable that has a very large range relative to others might dominante the clustering.

<div class="alert alert-block alert-success">
<b> Exercise 2: Produce a correlation coefficient matrix <a name="Exercise2"></a>  </b> Now you are tasked with producing a heatmap of correlation coefficients between the meteorological variables and fire extent. In the code snippet below I have imported the seaborn library used to produce the heatmap. For the rest of the code, you might want to revisit the examples in Practical 7.

When you you have finished the code for the other variables, you figure should look like the following:

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical8_corr.png?raw=true)

</div>

```python
import seaborn as sns
# calculate the correlation matrix
#------'INSERT CODE HERE'------
corr = data[['temp','RH','wind','rain','area']].corr()
# Now use an internal function within Seaborn called '.heatmap'
sns.heatmap(corr, xticklabels=corr.columns, yticklabels=corr.columns)
#------------------------------
# And we now need to show the plot.
plt.show()
```

![png](output_9_0.png)

#### 1.2.1) K-means cluster analysis <a name="Part1.2.1"></a>

K-means cluster analysis is perhaps the simplest method of all, but allows us to practice turning a dataset into one that contains a different number of clusters, members of which should have 'similar' properties. How we define the similarity between members can vary widely. Take the following [figure](https://jakevdp.github.io/PythonDataScienceHandbook/05.11-k-means.html):

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical_8_blue_kmeans.png?raw=true)

For this hypothetical 2D dataset, we can perhaps confidently calculate the correct number of clusters as 4. But, what if we simply dont know how many clusters we need or can't easily visualise all of the dimensions in our dataset? For our dataset, we can at least specify a number of clusrers and then visualise the properties of said clusters.

In the following code snippet we perform a number of steps to label each observation [row in our dataset] as belonging to a particular cluster. The label is an integer value, and the distinction between clusters will be performed on the values of temperature, humidity and fire area:

<div class="alert alert-block alert-info">

 - 1) Extract our variables of interest from the dataframe into a new Numpy matrix

 - 2) Specify how many clusters we want the Kmeans algorithm to find: You would be right in assuming that an algorithm might give us the number of clusters by default. Some do, but for now we have to specific this.

 - 3) Fit the clustering algorithm to our Numpy matrix: When we say we "fit" the Means algorithm (such as K-Means) to our data, we refer to the process of finding patterns or underlying structure by assigning data points to clusters based on their similarities. "Fitting" in this context means adjusting the model parameters — specifically, the positions of the cluster centroids — to best represent the natural groupings within the data. The algorithm iteratively optimizes these centroids by minimizing the distance between each data point and its assigned cluster center. The goal is to find a solution that "fits" the data by reducing the within-cluster variance, thereby creating well-defined clusters that capture meaningful patterns in the dataset.

 - 4) Extract the labels to which each row in our matrix has been assigned.
</div>

```python
from sklearn.cluster import KMeans
# Extract our variables of interest from the dataframe into a new Numpy matrix
numpy_matrix = data[['temp','RH','area']].values
# Specify how many clusters we want the Kmeans algorithm to find
clusterer=KMeans(n_clusters=4)
# Fit the clustering algorithm to our Numpy matrix
clusterer.fit(numpy_matrix)
# Extract the labels to which each row in our matrix has been assigned.
labels = clusterer.labels_

# In the dataframe 'data' we can store the labels from using K-means:
data['K-means label'] = labels
# For example the following simply prints the new dataframe column to the screen
data['K-means label']
```

    0      0
    1      1
    2      1
    3      0
    4      0
          ..
    512    1
    513    0
    514    0
    515    1
    516    1
    Name: K-means label, Length: 517, dtype: int32

Now let us look at the properties of these clusters by generating box-plots of values from our dataframe. We have already met multiple functions that can be applied to our dataframe. In Practical 7 we briefly produced box-plots of our dataframe using the:

```python
<<name of dataframe>>.boxplot(column=[<<names of columns>>])
```

command. We can also select a subset of values in the columns by asking the <code> boxplot </code> function to distinguish by a value found in a specific column. In the example below we expand the boxplot function to select values by K-means label through, for example:

```python
data.boxplot(column=['temp'], by=['K-means label'], ax=ax[0])
```
In this case we are asking Python to produce a boxplot of values in the column <code> temp </code> but also produce a number of seperate boxplots according the number of unique values given by the column <code> K-means label </code>.

Please check the following code snippet and then the box-plots. Do the collected properties of the different clusters allow you to distinguish between them? Do they 'look' different?

```python
fig, ax = plt.subplots(1, 3, figsize=(10, 5))
data.boxplot(column=['temp'], by=['K-means label'], ax=ax[0])
data.boxplot(column=['RH'], by=['K-means label'], ax=ax[1])
data.boxplot(column=['area'], by=['K-means label'], ax=ax[2]).set_yscale('log')

```

![png](output_13_0.png)

<div class="alert alert-block alert-success">
<b> Exercise 3: Create new dataframe with only positive values of fire area and repeat the above cluster analysis <a name="Exercise3"></a>  </b>

In this exercise you can copy the above code example, but you need to ensure operations are performed on a new set of datapoints from a new dataframe. Can you remember how we select a new dataframe according to some criteria on the values we want to work with? For example, if we wanted to create a new dataframe based on all values of <code> area </code> greater than 10, we might write:

```python
new_dataframe = data[data["area"] > 10.0]
```

In this exercise, you are asked to specify that the fire area should be positive. Once you have completed the code, you should arrive at the following figure:

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical_8_ex2.png?raw=true)

Please note the ordering may be different, but this is normal.

</div>

```python
#-------'INSERT CODE HERE'-------
data_new = data[data["area"] > 0]
numpy_matrix_new = data_new[['temp','RH','area']].values
clusterer=KMeans(n_clusters=4)
clusterer.fit(numpy_matrix_new)
labels = clusterer.labels_
data_new['K-means label'] = labels
#--------------------------------

data_new['K-means label']
#data['Operator'].value_counts().plot(kind='bar')
fig, ax = plt.subplots(1, 3, figsize=(10, 5))
data_new.boxplot(column=['temp'], by=['K-means label'], ax=ax[0])
data_new.boxplot(column=['RH'], by=['K-means label'], ax=ax[1])
data_new.boxplot(column=['area'], by=['K-means label'], ax=ax[2]).set_yscale('log')

```

    /Users/user/anaconda3/lib/python3.7/site-packages/ipykernel_launcher.py:6: SettingWithCopyWarning:
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead

    See the caveats in the documentation: http://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy

![png](output_15_1.png)

#### 1.2.2) Scaling data prior to clustering - 'Standardising'  <a name="Part1.2.2"></a>

We have mentioned 'distance' a few times with regards to clustering. In calculating a distance between points, we need to be mindful of the scale of each feature, or variable we are interested in. Taking the current dataset as an example, you can see that variable 'area' varies from less than 10 to 1000. On the other hand, variable 'temp' and 'RH' vary from 5 to 30 and 20 to 100 respectively. How do we know if 'area' is dominating the distance and thus clustering calculation? This is where scaling our data is important for distance-based clustering methods, such as **K-Means**, because these algorithms rely on calculating distances between data points to form clusters. If features in the dataset have different ranges or units (e.g., height in centimeters and weight in kilograms), features with larger ranges will dominate the distance calculations, causing biased clustering results. Scaling ensures that each feature contributes equally to the clustering process by standardizing them to comparable ranges, thus improving the algorithm's performance and ensuring fair treatment of all features.

---

Below are some common scaling techniques:

1. **Min-Max Scaling**: Rescales features to a fixed range, typically [0, 1].
2. **Standardization (Z-Score Scaling)**: Centers features to have a mean of 0 and a standard deviation of 1.
3. **Robust Scaling**: Uses the median and interquartile range, making it less sensitive to outliers.
4. **Max Abs Scaling**: Scales data to the range [-1, 1] based on the maximum absolute value of each feature.
5. **Log Scaling**: Applies a logarithmic transformation to reduce skewness in data with large ranges.

---

When reading literature and other examples in this space, you will find this is referred to as feature **stamdardisation** so it is worthwhile recognising interchangeable terms.
Below are some Python examples of applying different scaling (standardisation) techniques using the `sklearn` library.

```python
import numpy as np
import pandas as pd
from sklearn.preprocessing import MinMaxScaler, StandardScaler, RobustScaler, MaxAbsScaler

# Sample Data
data = pd.DataFrame({
    'Height (cm)': [150, 160, 170, 180, 190],
    'Weight (kg)': [50, 65, 70, 80, 90]
})

# 1. Min-Max Scaling
min_max_scaler = MinMaxScaler()
data_min_max_scaled = min_max_scaler.fit_transform(data)
print("Min-Max Scaled Data:")
print(data_min_max_scaled)

# 2. Standardization (Z-Score Scaling)
standard_scaler = StandardScaler()
data_standard_scaled = standard_scaler.fit_transform(data)
print("\nStandardized Data:")
print(data_standard_scaled)

# 3. Robust Scaling
robust_scaler = RobustScaler()
data_robust_scaled = robust_scaler.fit_transform(data)
print("\nRobust Scaled Data:")
print(data_robust_scaled)

# 4. Max Abs Scaling
max_abs_scaler = MaxAbsScaler()
data_max_abs_scaled = max_abs_scaler.fit_transform(data)
print("\nMax Abs Scaled Data:")
print(data_max_abs_scaled)
```

In the following code block we modify our previous example to use scaled data in the K-means algorithm. Run this and take a few minutes to visually check for any difference.

```python
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans

# Extract data for which we only have positive values of 'area'
data_new_scaled = data[data["area"] > 0]

# Extract our variables of interest from the dataframe into a new Numpy matrix
numpy_matrix = data_new_scaled[['temp', 'RH', 'area']].values

# Apply Standard Scaling to ensure all features contribute equally to the clustering
scaler = StandardScaler()
scaled_matrix = scaler.fit_transform(numpy_matrix)

# Specify how many clusters we want the KMeans algorithm to find
clusterer = KMeans(n_clusters=4)

# Fit the clustering algorithm to the scaled matrix
clusterer.fit(scaled_matrix)

# Extract the labels to which each row in our matrix has been assigned
labels = clusterer.labels_

# Store the KMeans labels back into the dataframe
data_new_scaled['K-means label (scaled)'] = labels

# Print the new dataframe column to the screen
print(data_new_scaled['K-means label (scaled)'])

#Create a new plot
fig, ax = plt.subplots(1, 3, figsize=(10, 5))
data_new_scaled.boxplot(column=['temp'], by=['K-means label (scaled)'], ax=ax[0])
data_new_scaled.boxplot(column=['RH'], by=['K-means label (scaled)'], ax=ax[1])
data_new_scaled.boxplot(column=['area'], by=['K-means label (scaled)'], ax=ax[2]).set_yscale('log')
```

    C:\Users\mccikdt3\anaconda3\envs\DEES_programming\lib\site-packages\pandas\core\frame.py:3607: SettingWithCopyWarning:
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead

    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      self._set_item(key, value)

    138    1
    139    1
    140    1
    141    3
    142    1
          ..
    509    0
    510    0
    512    3
    513    0
    514    0
    Name: K-means label (scaled), Length: 270, dtype: int32

![png](output_17_2.png)

Can you detect much of a difference in the outputs? It is difficult to assign any difference in a qualitative way. However we now have a slightly modified workflow as follows:

<div class="alert alert-block alert-info">

 - 1) Extract our variables of interest from the dataframe into a new Numpy matrix

 - 2) Scale the features (variables) prior to clustering: scaling our data is important for distance-based clustering methods, such as K-Means, because these algorithms rely on calculating distances between data points to form clusters. If features in the dataset have different ranges or units (e.g., height in centimeters and weight in kilograms), features with larger ranges will dominate the distance calculations, causing biased clustering results.

 - 3) Specify how many clusters we want the Kmeans algorithm to find: You would be right in assuming that an algorithm might give us the number of clusters by default. Some do, but for now we have to specific this.

 - 4) Fit the clustering algorithm to our Numpy matrix: When we say we "fit" the Means algorithm (such as K-Means) to our data, we refer to the process of finding patterns or underlying structure by assigning data points to clusters based on their similarities. "Fitting" in this context means adjusting the model parameters — specifically, the positions of the cluster centroids — to best represent the natural groupings within the data. The algorithm iteratively optimizes these centroids by minimizing the distance between each data point and its assigned cluster center. The goal is to find a solution that "fits" the data by reducing the within-cluster variance, thereby creating well-defined clusters that capture meaningful patterns in the dataset.

 - 5) Extract the labels to which each row in our matrix has been assigned.
</div>

In the following section we work with data for which we know what the answers are. Before that, why not try to modify the example above and use a different scaler function.

### 1.3) Working with 'labelled' data <a name="Part1.3"></a>

Before applying clustering algorithms, a significant amount of time is typically spent exploring and understanding the data. This process, which we refer to as exploratory data analysis, or EDA, is crucial because clustering algorithms are highly sensitive to the scale, distribution, and structure of the data. Tasks such as handling missing values, removing outliers, normalizing features, and selecting relevant variables can greatly influence the quality of the clusters formed. Additionally, visualizing the data through plots and dimensionality reduction techniques can help uncover patterns and inform the choice of clustering parameters, like the number of clusters. In many cases, the success of a clustering task depends less on the algorithm itself and more on how well we prepare and understand the data beforehand.

In the next example we are going to work with a dataset for which the cluster label is already known. You may well ask, well, if the cluster label is already known then why do we need to use cluster analysis? These labelled datasets are crucial to understand the accuracy of different clustering approaches. Moreover, if you had a small amount of data from controlled experiments you could test the accuracy of clustering approaches before applying this to lots of data for which you dont have the answer.

The next dataset we will work with is a dataset of [acoustic features extracted from syllables of anuran (frogs) calls, including the family, the genus, and the species labels (multilabel). ](https://archive.ics.uci.edu/dataset/406/anuran+calls+mfccs). For more information on the method used for generating the data, you can follow the link provided. For now, we load this data into a Pandas dataframe.

```python
# Load the Air BnB data
if 'google.colab' in str(get_ipython()):
    data_frogs = pd.read_csv('https://raw.githubusercontent.com/loftytopping/DEES_programming_course/master/data/Frogs_MFCCs.csv')
    data_frogs.head()
else:
    data_frogs = pd.read_csv("data/Frogs_MFCCs.csv")
    data_frogs.head()

# Preview the first 5 lines of the loaded data
data_frogs.head()
#data_NYC.columns.values
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
      <th>MFCCs_ 1</th>
      <th>MFCCs_ 2</th>
      <th>MFCCs_ 3</th>
      <th>MFCCs_ 4</th>
      <th>MFCCs_ 5</th>
      <th>MFCCs_ 6</th>
      <th>MFCCs_ 7</th>
      <th>MFCCs_ 8</th>
      <th>MFCCs_ 9</th>
      <th>MFCCs_10</th>
      <th>...</th>
      <th>MFCCs_17</th>
      <th>MFCCs_18</th>
      <th>MFCCs_19</th>
      <th>MFCCs_20</th>
      <th>MFCCs_21</th>
      <th>MFCCs_22</th>
      <th>Family</th>
      <th>Genus</th>
      <th>Species</th>
      <th>RecordID</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.0</td>
      <td>0.152936</td>
      <td>-0.105586</td>
      <td>0.200722</td>
      <td>0.317201</td>
      <td>0.260764</td>
      <td>0.100945</td>
      <td>-0.150063</td>
      <td>-0.171128</td>
      <td>0.124676</td>
      <td>...</td>
      <td>-0.108351</td>
      <td>-0.077623</td>
      <td>-0.009568</td>
      <td>0.057684</td>
      <td>0.118680</td>
      <td>0.014038</td>
      <td>Leptodactylidae</td>
      <td>Adenomera</td>
      <td>AdenomeraAndre</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1.0</td>
      <td>0.171534</td>
      <td>-0.098975</td>
      <td>0.268425</td>
      <td>0.338672</td>
      <td>0.268353</td>
      <td>0.060835</td>
      <td>-0.222475</td>
      <td>-0.207693</td>
      <td>0.170883</td>
      <td>...</td>
      <td>-0.090974</td>
      <td>-0.056510</td>
      <td>-0.035303</td>
      <td>0.020140</td>
      <td>0.082263</td>
      <td>0.029056</td>
      <td>Leptodactylidae</td>
      <td>Adenomera</td>
      <td>AdenomeraAndre</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1.0</td>
      <td>0.152317</td>
      <td>-0.082973</td>
      <td>0.287128</td>
      <td>0.276014</td>
      <td>0.189867</td>
      <td>0.008714</td>
      <td>-0.242234</td>
      <td>-0.219153</td>
      <td>0.232538</td>
      <td>...</td>
      <td>-0.050691</td>
      <td>-0.023590</td>
      <td>-0.066722</td>
      <td>-0.025083</td>
      <td>0.099108</td>
      <td>0.077162</td>
      <td>Leptodactylidae</td>
      <td>Adenomera</td>
      <td>AdenomeraAndre</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1.0</td>
      <td>0.224392</td>
      <td>0.118985</td>
      <td>0.329432</td>
      <td>0.372088</td>
      <td>0.361005</td>
      <td>0.015501</td>
      <td>-0.194347</td>
      <td>-0.098181</td>
      <td>0.270375</td>
      <td>...</td>
      <td>-0.136009</td>
      <td>-0.177037</td>
      <td>-0.130498</td>
      <td>-0.054766</td>
      <td>-0.018691</td>
      <td>0.023954</td>
      <td>Leptodactylidae</td>
      <td>Adenomera</td>
      <td>AdenomeraAndre</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1.0</td>
      <td>0.087817</td>
      <td>-0.068345</td>
      <td>0.306967</td>
      <td>0.330923</td>
      <td>0.249144</td>
      <td>0.006884</td>
      <td>-0.265423</td>
      <td>-0.172700</td>
      <td>0.266434</td>
      <td>...</td>
      <td>-0.048885</td>
      <td>-0.053074</td>
      <td>-0.088550</td>
      <td>-0.031346</td>
      <td>0.108610</td>
      <td>0.079244</td>
      <td>Leptodactylidae</td>
      <td>Adenomera</td>
      <td>AdenomeraAndre</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 26 columns</p>
</div>

There are many columns that have no information that is directly useful to us, unless you are already familiar with how the data has been generated. You should see we have three columns that provide a target label. These are 'Family', 'Genus' and 'Species'. We dont need to jump into the difference between each, but it might be useful to know that:

- Family is a broader category that includes multiple related genera.
- Genus is a more specific group within a family that contains closely related species.
- Species is the most specific rank and refers to individual organisms that can reproduce together.

This hierarchical system helps biologists classify and understand the relationships between different organisms in the natural world. In the following exercise you are asked to generate a list of unique entries in both columns, whilst also generating

<div class="alert alert-block alert-success">
<b> Exercise 4a: Generate lists of unique entries in columns 'Family', 'Genus' and 'Species' <a name="Exercise4a"></a>  </b>

If you recall in Practical 6 we started to use the function of a dataframe:

```python
.value_counts()
```

Apply this here.

</div>

```python
#-------'INSERT CODE HERE'-------
print("\n List of unique Family entries : \n",data_frogs['Family'].value_counts())
print("Number of of unique Family entries : \n",data_frogs['Family'].value_counts().size)

print("\n List of unique Genus entries : \n",data_frogs['Genus'].value_counts())
print("Number of of unique Genus entries : \n",data_frogs['Genus'].value_counts().size)

print("\n List of unique Species entries : \n",data_frogs['Species'].value_counts())
print("Number of of unique Species entries : \n",data_frogs['Species'].value_counts().size)
#------------------------------
```

     List of unique Family entries :
     Leptodactylidae    4420
    Hylidae            2165
    Dendrobatidae       542
    Bufonidae            68
    Name: Family, dtype: int64
    Number of of unique Family entries :
     4

     List of unique Genus entries :
     Adenomera        4150
    Hypsiboas        1593
    Ameerega          542
    Dendropsophus     310
    Leptodactylus     270
    Scinax            148
    Osteocephalus     114
    Rhinella           68
    Name: Genus, dtype: int64
    Number of of unique Genus entries :
     8

     List of unique Species entries :
     AdenomeraHylaedactylus    3478
    HypsiboasCordobae         1121
    AdenomeraAndre             672
    Ameeregatrivittata         542
    HypsiboasCinerascens       472
    HylaMinuta                 310
    LeptodactylusFuscus        270
    ScinaxRuber                148
    OsteocephalusOophagus      114
    Rhinellagranulosa           68
    Name: Species, dtype: int64
    Number of of unique Species entries :
     10

Let's focus primarily on the 'Family' label. In the next exercise, fill in the blanks to visualise the distribution of values for each family label through a loop. Again we need to use properties of a dataframe we have used in previous notebooks to isolate data associated with a given condition. If you need to, please use the code provided in the solutions version of this notebook. In this example we are using a single figure to visualise the distribution of a selected 'feature' (e.g. MFCCs_17') as a function of 'Family' label. Much of the visualisation code is provided, but please fill in code where required to generate the unique dataframes.

<div class="alert alert-block alert-success">
<b> Exercise 4b: Generate a set of figures that highlight the distribution of individual features as a function of Family label. <a name="Exercise4b"></a>  </b>

You will need to complete the list of feature names, ensuring each name matches the entry in the dataframe. If you would like to test the figure for a single feature, the following Python code will work:

```python
# Create a histogram with hue controlled by the Family label
sns.histplot(data=data_frogs, x='MCCs_17', hue='Family', kde=True, element="step")
plt.title(f'Distribution of {feature} by Family')
plt.show()
```

</div>

```python
#-------'INSERT CODE HERE'-------
# Create a list of all column names to iterate through - make sure these are the same as entered in the dataframe
column_list=['MFCCs_ 1', 'MFCCs_ 2', 'MFCCs_ 3', 'MFCCs_ 4', 'MFCCs_ 5', 'MFCCs_ 6',
       'MFCCs_ 7', 'MFCCs_ 8', 'MFCCs_ 9', 'MFCCs_10', 'MFCCs_11', 'MFCCs_12',
       'MFCCs_13', 'MFCCs_14', 'MFCCs_15', 'MFCCs_16', 'MFCCs_17', 'MFCCs_18',
       'MFCCs_19', 'MFCCs_20', 'MFCCs_21', 'MFCCs_22']

for feature in column_list:
    # Create a histogram with hue controlled by the Family label
    sns.histplot(data=data_frogs, x=feature, hue='Family', kde=True, element="step")
    plt.title(f'Distribution of {feature} by Family')
    plt.show()
#------------------------------
```

![png](output_26_0.png)

![png](output_26_1.png)

#### 1.4) Dimension reduction <a name="Part1.4"></a>

The above figures provide some interesting and useful insights in to our data. We can see that some features are clearly different for a given family label. This means these features are going to be useful in applying cluster analysis. However visualising multiple features can be tricky. We can use an approach called **Dimensionality Reduction** to try and visualise our entire collection of features in a new space.

Briefly, dimensionality reduction is a process used in machine learning to simplify high-dimensional datasets by transforming them into a lower-dimensional space while retaining as much of the original data's meaningful information as possible. High-dimensional data can be difficult to interpret, prone to overfitting, and computationally expensive to process. By reducing the number of features (or dimensions), we aim to improve model performance, reduce noise, and make the data easier to visualize and understand.

##### Why Are the New Features Considered 'Latent'?

The new features generated during dimensionality reduction are often referred to as latent features because they are not directly observed in the original dataset. Instead, they are abstract, derived representations that capture the underlying structure or patterns in the data. For example, in techniques like Principal Component Analysis (PCA), the new features (principal components) are linear combinations of the original features. These latent features are not tied to any specific real-world measurement but are mathematical constructs that explain the variance in the data. This makes them valuable for uncovering hidden relationships, but it also means they may be harder to interpret compared to the original features.

Lets apply PCA to our current dataset and show how to visualise the data in a new way:

```python
#Import the relevant libraries
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler

#Extract the features and target 'Family'
features = data_frogs[['MFCCs_ 1', 'MFCCs_ 2', 'MFCCs_ 3', 'MFCCs_ 4', 'MFCCs_ 5', 'MFCCs_ 6',
       'MFCCs_ 7', 'MFCCs_ 8', 'MFCCs_ 9', 'MFCCs_10', 'MFCCs_11', 'MFCCs_12',
       'MFCCs_13', 'MFCCs_14', 'MFCCs_15', 'MFCCs_16', 'MFCCs_17', 'MFCCs_18',
       'MFCCs_19', 'MFCCs_20', 'MFCCs_21', 'MFCCs_22']]
target = data_frogs['Family']

# Step 1: Standardize the features - this is a process of ensuring our data is normalised
scaler = StandardScaler()
features_scaled = scaler.fit_transform(features)

# Step 2: Apply PCA to reduce to 2 components
pca = PCA(n_components=2)
pca_components = pca.fit_transform(features_scaled)

# Step 3: Create a new dataframe with the PCA components and target label
pca_df = pd.DataFrame(data=pca_components, columns=['PC1', 'PC2'])
pca_df['target'] = target

# Step 4: Plot the PCA results using Seaborn
plt.figure(figsize=(10, 6))
sns.scatterplot(data=pca_df, x='PC1', y='PC2', hue='target', palette='Set2')
plt.title('PCA: First Two Principal Components')
plt.show()

```

![png](output_28_0.png)

We can see some level of seperation between different targets, but still some overlap. In any case, in the following exercise we ask you to repeat this PCA analysis but on a different target variable.

<div class="alert alert-block alert-success">
<b> Exercise 5: Apply Principal Component Analysis to the target label 'Genus'. <a name="Exercise5"></a>  </b>

Use the code provided above but for the 'Genus' label.

</div>

```python
#Import the relevant libraries
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler

#Extract the features and target 'Family'
features = data_frogs[['MFCCs_ 1', 'MFCCs_ 2', 'MFCCs_ 3', 'MFCCs_ 4', 'MFCCs_ 5', 'MFCCs_ 6',
       'MFCCs_ 7', 'MFCCs_ 8', 'MFCCs_ 9', 'MFCCs_10', 'MFCCs_11', 'MFCCs_12',
       'MFCCs_13', 'MFCCs_14', 'MFCCs_15', 'MFCCs_16', 'MFCCs_17', 'MFCCs_18',
       'MFCCs_19', 'MFCCs_20', 'MFCCs_21', 'MFCCs_22']]
target = data_frogs['Genus']

# Step 1: Standardize the features - this is a process of ensuring our data is normalised
scaler = StandardScaler()
features_scaled = scaler.fit_transform(features)

# Step 2: Apply PCA to reduce to 2 components
pca = PCA(n_components=2)
pca_components = pca.fit_transform(features_scaled)

# Step 3: Create a new dataframe with the PCA components and target label
pca_df = pd.DataFrame(data=pca_components, columns=['PC1', 'PC2'])
pca_df['Genus'] = target

# Step 4: Plot the PCA results using Seaborn
plt.figure(figsize=(10, 6))
sns.scatterplot(data=pca_df, x='PC1', y='PC2', hue='Genus', palette='Set2')
plt.title('PCA: First Two Principal Components')
plt.show()

```

![png](output_31_0.png)

### 1.4) Evaluating the accuracy of a clustering algorithm with 'labelled' data <a name="Part1.4"></a>

In this section we consolidate most of the above and determine how accurate K-means is in identifying distinct groups. We will focus first on using the 'Family' target. The entire code to do this is provided shortly but please first read through the worklow before running it. The key steps are as follows:

1. Prepare the features and target variables
2. Standardise the dataset
3. Apply dimension reduction
4. Apply K-means clustering
5. Map clusters to true labels
6. Evaluate accuracy

---

#### Step 1: Prepare the features and target variables**
We first separate the features (22 columns) from the target label in the same way we did above.
```python
# Separate features and target
features = data_frogs[['MFCCs_ 1', 'MFCCs_ 2', 'MFCCs_ 3', 'MFCCs_ 4', 'MFCCs_ 5', 'MFCCs_ 6',
       'MFCCs_ 7', 'MFCCs_ 8', 'MFCCs_ 9', 'MFCCs_10', 'MFCCs_11', 'MFCCs_12',
       'MFCCs_13', 'MFCCs_14', 'MFCCs_15', 'MFCCs_16', 'MFCCs_17', 'MFCCs_18',
       'MFCCs_19', 'MFCCs_20', 'MFCCs_21', 'MFCCs_22']]
target = data_frogs['Family']
```

---

#### Step 2: Standardize the Features**

Since K-means is distance-based, we must standardize the features to ensure all variables contribute equally to the clustering.
```python
from sklearn.preprocessing import StandardScaler

# Standardize features
scaler = StandardScaler()
features_scaled = scaler.fit_transform(features)
```

---

#### Step 3: Apply dimension reduction**

Since K-means is distance-based, we must standardize the features to ensure all variables contribute equally to the clustering.
```python
from sklearn.decomposition import PCA

pca = PCA(n_components=2)
pca_components = pca.fit_transform(features_scaled)

# Create a new dataframe with the PCA components and target label
pca_df = pd.DataFrame(data=pca_components, columns=['PC1', 'PC2'])
pca_df['Genus'] = target

```

---

#### Step 4: Apply K-means Clustering**
We apply K-means clustering, specifying the number of clusters to match the number of unique values in the target. In this case, we know there are 4 unique entries for 'Family'
```python
from sklearn.cluster import KMeans

# Apply K-means with 4 clusters
kmeans = KMeans(n_clusters=4, random_state=42)
clusters = kmeans.fit_predict(pca_components)
```

---

#### Step 5: Map Clusters to True Labels**
K-means assigns arbitrary cluster IDs, so we map the clusters to the most common true labels using the mode.
```python
def map_clusters_to_labels(predicted, true):
    labels = np.zeros_like(predicted)
    for i in np.unique(predicted):
        mask = predicted == i
        labels[mask] = np.bincount(true[mask]).argmax()
    return labels

# Map clusters to true labels
predicted_labels = map_clusters_to_labels(clusters, true_labels_encoded)

# Convert mapped numeric labels back to original string labels
predicted_labels = le.inverse_transform(predicted_labels)
```

---

#### Step 6: Evaluate Accuracy**
We calculate the accuracy by comparing the predicted labels with the true labels. The accuracy_score() function compares the true labels with the mapped predicted labels. Note that clustering labels retrieved from K-means are arbitrary, so mapping the predicted labels to the closest matching true labels is necessary for accuracy measurement. The confusion_matrix() function shows how well the clusters match the true classes. A confusion matrix is a table that summarizes the performance of a classification model by comparing its predicted labels with the actual labels. Each row represents the instances of an actual class, while each column represents the instances of a predicted class. This is best understood by running through the code example given below and then the follow-up exercise.

```python
from sklearn.metrics import accuracy_score, confusion_matrix

# Calculate accuracy
accuracy = accuracy_score(target, predicted_labels)
print(f'K-means Accuracy: {accuracy:.2f}')

# Print confusion matrix
conf_matrix = confusion_matrix(target, predicted_labels)
print("Confusion Matrix:")
print(conf_matrix)

# Plot confusion matrix using seaborn heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(conf_matrix, annot=True, fmt='d', cmap='Blues', xticklabels=set(target), yticklabels=set(target))
plt.title('Confusion Matrix')
plt.xlabel('Predicted Label')
plt.ylabel('True Label')
plt.show()
```
```

---

```python
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA
from sklearn.cluster import KMeans
from scipy.stats import mode
from sklearn.metrics import accuracy_score, confusion_matrix
import seaborn as sns
from sklearn.preprocessing import LabelEncoder
import numpy as np

# 1) Separate features and target
features = data_frogs[['MFCCs_ 1', 'MFCCs_ 2', 'MFCCs_ 3', 'MFCCs_ 4', 'MFCCs_ 5', 'MFCCs_ 6',
       'MFCCs_ 7', 'MFCCs_ 8', 'MFCCs_ 9', 'MFCCs_10', 'MFCCs_11', 'MFCCs_12',
       'MFCCs_13', 'MFCCs_14', 'MFCCs_15', 'MFCCs_16', 'MFCCs_17', 'MFCCs_18',
       'MFCCs_19', 'MFCCs_20', 'MFCCs_21', 'MFCCs_22']]
target = data_frogs['Family']

# Convert string labels to numeric labels
le = LabelEncoder()
true_labels_encoded = le.fit_transform(target)

# Step 2: Standardize the Features
# Standardize features
scaler = StandardScaler()
features_scaled = scaler.fit_transform(features)

# Step 3: Apply dimension reduction
pca = PCA(n_components=2)
pca_components = pca.fit_transform(features_scaled)

# Create a new dataframe with the PCA components and target label
pca_df = pd.DataFrame(data=pca_components, columns=['PC1', 'PC2'])
pca_df['Family'] = target

# Step 4: Apply K-means Clustering**
kmeans = KMeans(n_clusters=4, random_state=42)
clusters = kmeans.fit_predict(pca_components)

# Step 5: Map Clusters to True Labels**
def map_clusters_to_labels(predicted, true):
    labels = np.zeros_like(predicted)
    for i in np.unique(predicted):
        mask = predicted == i
        labels[mask] = np.bincount(true[mask]).argmax()
    return labels

# Map clusters to true labels
predicted_labels = map_clusters_to_labels(clusters, true_labels_encoded)

# Convert mapped numeric labels back to original string labels
predicted_labels = le.inverse_transform(predicted_labels)

# Step 6: Evaluate Accuracy
# Calculate accuracy
accuracy = accuracy_score(target, predicted_labels)
print(f'K-means Accuracy: {accuracy:.2f}')

# Print confusion matrix
conf_matrix = confusion_matrix(target, predicted_labels)
print("Confusion Matrix:")
print(conf_matrix)

# Plot the confusion matrix as a heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(conf_matrix, annot=True, fmt='d', cmap='Blues', xticklabels=set(target), yticklabels=set(target))
# Rotate the y-axis labels to horizontal
plt.yticks(rotation=0)
plt.title('Confusion Matrix')
plt.xlabel('Predicted Label')
plt.ylabel('True Label')
plt.show()
```

    K-means Accuracy: 0.76
    Confusion Matrix:
    [[   0    0   68    0]
     [   0    0  542    0]
     [   0    0 2029  136]
     [   0    0  954 3466]]

![png](output_33_1.png)

A confusion matrix is a table that allows us to visualize the performance of a classification algorithm. Each row represents the instances of the actual class, while each column represents the instances of the predicted class.

**Components of the Confusion Matrix:**

- **True Positives (TP):** Correctly predicted positive cases.
- **True Negatives (TN):** Correctly predicted negative cases.
- **False Positives (FP):** Incorrectly predicted positive cases (Type I error).
- **False Negatives (FN):** Incorrectly predicted negative cases (Type II error).

**Metrics Derived from the Confusion Matrix:**

- **Accuracy:** The proportion of correct predictions out of all predictions.

$$ \text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN} $$

In our example we can see that K-means clustering is only 76% accurate; much of this dominated by the imbalanced 'Bufonidae' class.

<div class="alert alert-block alert-success">
<b> Exercise 6: Apply K-means to the target label 'Genus' with no dimension reduction. <a name="Exercise6"></a>  </b>

Repeat the K-means clustering workflow on our labelled data with two distinct changes:

     - Use the 'Genus' label as the target
     - Do not apply PCA for dimension reduction

Do you obtain an accuray of 80%?

</div>

```python
#-------'INSERT CODE HERE'-------

from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA
from sklearn.cluster import KMeans
from scipy.stats import mode
from sklearn.metrics import accuracy_score, confusion_matrix
import seaborn as sns
from sklearn.preprocessing import LabelEncoder
import numpy as np

# 1) Separate features and target
features = data_frogs[['MFCCs_ 1', 'MFCCs_ 2', 'MFCCs_ 3', 'MFCCs_ 4', 'MFCCs_ 5', 'MFCCs_ 6',
       'MFCCs_ 7', 'MFCCs_ 8', 'MFCCs_ 9', 'MFCCs_10', 'MFCCs_11', 'MFCCs_12',
       'MFCCs_13', 'MFCCs_14', 'MFCCs_15', 'MFCCs_16', 'MFCCs_17', 'MFCCs_18',
       'MFCCs_19', 'MFCCs_20', 'MFCCs_21', 'MFCCs_22']]
target = data_frogs['Genus']

# Convert string labels to numeric labels
le = LabelEncoder()
true_labels_encoded = le.fit_transform(target)

# Step 2: Standardize the Features
# Standardize features
scaler = StandardScaler()
features_scaled = scaler.fit_transform(features)

# Step 3: Apply dimension reduction
# pca = PCA(n_components=2)
# pca_components = pca.fit_transform(features_scaled)

# Create a new dataframe with the PCA components and target label
# pca_df = pd.DataFrame(data=pca_components, columns=['PC1', 'PC2'])
# pca_df['Genus'] = target

# Step 4: Apply K-means Clustering**
kmeans = KMeans(n_clusters=8, random_state=42)
clusters = kmeans.fit_predict(pca_components)

# Step 5: Map Clusters to True Labels**
def map_clusters_to_labels(predicted, true):
    labels = np.zeros_like(predicted)
    for i in np.unique(predicted):
        mask = predicted == i
        labels[mask] = np.bincount(true[mask]).argmax()
    return labels

# Map clusters to true labels
predicted_labels = map_clusters_to_labels(clusters, true_labels_encoded)

# Convert mapped numeric labels back to original string labels
predicted_labels = le.inverse_transform(predicted_labels)

# Step 6: Evaluate Accuracy
# Calculate accuracy
accuracy = accuracy_score(target, predicted_labels)
print(f'K-means Accuracy: {accuracy:.2f}')

# Print confusion matrix
conf_matrix = confusion_matrix(target, predicted_labels)
print("Confusion Matrix:")
print(conf_matrix)

# Plot the confusion matrix as a heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(conf_matrix, annot=True, fmt='d', cmap='Blues', xticklabels=set(target), yticklabels=set(target))
# Rotate the y-axis labels to horizontal
plt.yticks(rotation=0)
plt.title('Confusion Matrix')
plt.xlabel('Predicted Label')
plt.ylabel('True Label')
plt.show()

#------------------------------
```

    K-means Accuracy: 0.80
    Confusion Matrix:
    [[3965  120    0   65    0    0    0    0]
     [ 227  260    0   55    0    0    0    0]
     [  87  122    0  101    0    0    0    0]
     [  42    3    0 1548    0    0    0    0]
     [ 176   18    0   76    0    0    0    0]
     [  69    0    0   45    0    0    0    0]
     [   9    0    0   59    0    0    0    0]
     [   8   19    0  121    0    0    0    0]]

![png](output_36_1.png)

## 2) Introduction to Supervised Machine Learning <a name="Part2"></a>

Before we finish, it is worthwhile taking a look at how to apply supervised machine learning algorithms. Supervised learning is a fundamental branch of machine learning where models are trained on labeled datasets, meaning each input is paired with a known output. This approach enables the model to learn the relationship between inputs and outputs, facilitating accurate predictions on new, unseen data. Common applications include classification tasks, such as email spam detection, and regression tasks, like forecasting sales figures. In our eaxmple, we could develop a workflow to predict, say, the 'Genus' as a function of measured features. In this case, it might be useful to train a method on the data we already have...where the type of frog id know...and then apply it to new data obtained from complex ambient experiments.

Supervised learning involves training models on labeled datasets, where each training example is paired with an output label. The goal is to learn a mapping from inputs to outputs that can be used to predict the labels of new, unseen data. Supervised learning algorithms are broadly categorized into:

- **Classification Algorithms:** Used when the output variable is a category, such as 'spam' or 'not spam'.
- **Regression Algorithms:** Used when the output variable is a continuous value, such as predicting house prices.

There are a number of methods available for each task:

Classification Algorithms:
 - Decision Trees: Models that split data into branches to make decisions based on feature values.
 - Support Vector Machines (SVM): Algorithms that identify the optimal boundary separating different classes.
 - k-Nearest Neighbors (k-NN): Methods that classify data points based on the majority class among their nearest neighbors.
 - Naive Bayes: Probabilistic classifiers based on Bayes' theorem, assuming feature independence.
 - **Neural Networks: Computational models inspired by the human brain, capable of capturing complex patterns in data.**

Regression Algorithms:
 - Linear Regression: Models that establish a linear relationship between input features and the target variable.
 - Ridge and Lasso Regression: Variants of linear regression that incorporate regularization to prevent overfitting.
 - Polynomial Regression: Models that capture non-linear relationships by incorporating polynomial terms of the input features.
 - Support Vector Regression (SVR): An extension of SVM for predicting continuous outcomes.
 - Decision Tree Regression: Models that predict continuous values by learning decision rules from the features.

### 2.1) Train, test and validate <a name="Part2.1"></a>

There is an important step we will now introduce in our approach to fitting machine learning models. Datasets are typically divided into three subsets: training, validation, and test sets.
 - The training set is used to fit the model's parameters, enabling it to learn patterns within the data.
 - The validation set assists in tuning hyperparameters and provides an unbiased evaluation during model development, helping to prevent overfitting.
 - Finally, the test set offers an independent assessment of the model's performance, ensuring it generalizes well to new, unseen data.

This is perhaps best visualised in the following [schematic](https://medium.com/@rahulchavan4894/understanding-train-test-and-validation-dataset-split-in-simple-quick-terms-5a8630fe58c8):

<div>
<img src="https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical_9_figure3.png?raw=true" width="600"/>
</div>

This structured division is crucial for developing robust and reliable machine learning models. There are a number of new terms here which you may have not come across before. For example, **Hyperparameters** are the configurable parameters set before the training process of a machine learning (ML) model. They control the behaviour of the training algorithm and impact on the model’s performance. Unlike regular parameters, which are learned by the model during training (e.g., weights in a neural network), hyperparameters must be defined before training starts.

In simple terms:

 - Parameters are learned from the data.
 - Hyperparameters are set by you before training. For example, the number of layers in a neural network.

Do not worry, this section is to act as an introductory demonstration to applying supervised methods. Machine learning, and subsets of the field, require modules and programmes by themselves. However by building your, poentially, first supervised method you could dive much deeper into this expanding area of research. In the following code block we train and validate a common supervised learning algorithm known as random forests.

### 2.2) Predicting Labels from Features using Random Forests in scikit-learn <a name="Part2.2"></a>

In the following example, we will use the existing Frog dataset to demonstrate how to build on our existing examples and:

1. Split the data into training and testing sets.
2. Train a Random Forest classification model.
3. Predict labels for new data points.
4. Evaluate the model using accuracy and a confusion matrix.

The goal is to classify each sample into one of labels held within the 'Family' label:

```python
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, confusion_matrix
import seaborn as sns

features = data_frogs[['MFCCs_ 1', 'MFCCs_ 2', 'MFCCs_ 3', 'MFCCs_ 4', 'MFCCs_ 5', 'MFCCs_ 6',
       'MFCCs_ 7', 'MFCCs_ 8', 'MFCCs_ 9', 'MFCCs_10', 'MFCCs_11', 'MFCCs_12',
       'MFCCs_13', 'MFCCs_14', 'MFCCs_15', 'MFCCs_16', 'MFCCs_17', 'MFCCs_18',
       'MFCCs_19', 'MFCCs_20', 'MFCCs_21', 'MFCCs_22']]
target = data_frogs['Family']

# 1) Split the data into training and testing sets.
X = features
y = target
# Split the data (80% train, 20% test)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

print(f"Training samples: {len(X_train)}")
print(f"Testing samples: {len(X_test)}")

# Step 2: Train a Random Forest classification model.
# Initialize the Random Forest model
rf_model = RandomForestClassifier(n_estimators=100, random_state=42)
# Train the model
rf_model.fit(X_train, y_train)
print("Random Forest model trained successfully!")

# Step 3: Predict labels for new data points.
# Predict the species for the test set
predictions = rf_model.predict(X_test)

# Print the first few predictions
print("Predicted labels:", predictions[:5])
print("True labels:", y_test[:5])

# Step 4: Apply K-means Clustering**
# Calculate accuracy
accuracy = accuracy_score(y_test, predictions)
print(f"Accuracy: {accuracy:.2f}")

# Generate a confusion matrix
conf_matrix = confusion_matrix(y_test, predictions)
print("Confusion Matrix:")
print(conf_matrix)

# Plot the confusion matrix as a heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(conf_matrix, annot=True, fmt='d', cmap='Blues', xticklabels=set(target), yticklabels=set(target))
# Rotate the y-axis labels to horizontal
plt.yticks(rotation=0)
plt.title('Confusion Matrix')
plt.xlabel('Predicted Label')
plt.ylabel('True Label')
plt.show()
```

    Training samples: 5756
    Testing samples: 1439
    Random Forest model trained successfully!
    Predicted labels: ['Leptodactylidae' 'Hylidae' 'Hylidae' 'Leptodactylidae' 'Leptodactylidae']
    True labels: 3340    Leptodactylidae
    5108            Hylidae
    6524            Hylidae
    3649    Leptodactylidae
    1617    Leptodactylidae
    Name: Family, dtype: object
    Accuracy: 0.99
    Confusion Matrix:
    [[ 12   0   3   2]
     [  0 105   1   0]
     [  0   0 413   9]
     [  0   1   5 888]]

![png](output_38_1.png)

What does this visulisation tell us? We are able to reach an accuracy of 99% which sounds very high. As noted previously, from this point on there is much more to learn about machine learning. You may be wondering what the variable n_estimators refers to in the line:

```python
# Initialize the Random Forest model
rf_model = RandomForestClassifier(n_estimators=100, random_state=42)
```

This is one the hyperparameters we mentioned earlier. In this case, the number of estimators refers to the number of individual trees in the forest :). The [illustration](https://medium.com/@roiyeho/random-forests-98892261dc49) below tries to explain this:

<div>
<img src="https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical_9_figure3.png?raw=true" width="600"/>
</div>

Briefly, in a **Random Forest**, the number of estimators refers to the number of **decision trees** that the algorithm builds before making predictions. It is controlled by the parameter `n_estimators` in `RandomForestClassifier`. Each tree is trained on a random subset of the data and features, and the final prediction is made by **aggregating the outputs of all the trees** (via majority voting for classification or averaging for regression).

#### Why the Number of Estimators Matters
- **More trees** generally improve the model’s accuracy because the forest becomes more robust and less prone to overfitting individual samples.
- **Too few trees** can result in an underfit model, missing important patterns in the data.
- **Too many trees** increase computational cost and training time without significant performance gains after a certain point.

#### How It Works in Practice
1. **During Training**: Each tree in the forest is trained on a different random subset of the data (bagging).
2. **During Prediction**: For classification, each tree votes on the predicted class. The class with the most votes is the final prediction.

#### Key Trade-off
- **Higher `n_estimators` improves performance but increases computation time**.
- In practice, values between **100 and 500 trees** are typically sufficient for most problems.

#### Example: Understanding the Impact of `n_estimators`
The effect of `n_estimators` on accuracy can be explored by training Random Forest models with different numbers of trees and comparing their performance.

A number of resources are provided at the bottom of this notebook should you be interested. This includes learning how to work with images, detect objects, work with large language models (LLMs) and so on. To complete this notebook, try to tackle the exercise given below in which you are tasked with evaluating the accuracy of a random forest classifier for 'Species' label.

<div class="alert alert-block alert-success">
<b> Exercise 7: Evaluate the accuracy of a Random Forest Classifier in predicting the target label 'Species'. <a name="Exercise7"></a>  </b>

Repeat the supervised workflow on our labelled data with one distinct changes:

     - Use the 'Species' label as the target

</div>

```python
#-------'INSERT CODE HERE'-------

from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, confusion_matrix
import seaborn as sns

features = data_frogs[['MFCCs_ 1', 'MFCCs_ 2', 'MFCCs_ 3', 'MFCCs_ 4', 'MFCCs_ 5', 'MFCCs_ 6',
       'MFCCs_ 7', 'MFCCs_ 8', 'MFCCs_ 9', 'MFCCs_10', 'MFCCs_11', 'MFCCs_12',
       'MFCCs_13', 'MFCCs_14', 'MFCCs_15', 'MFCCs_16', 'MFCCs_17', 'MFCCs_18',
       'MFCCs_19', 'MFCCs_20', 'MFCCs_21', 'MFCCs_22']]
target = data_frogs['Species']

# 1) Split the data into training and testing sets.
X = features
y = target
# Split the data (80% train, 20% test)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

print(f"Training samples: {len(X_train)}")
print(f"Testing samples: {len(X_test)}")

# Step 2: Train a Random Forest classification model.
# Initialize the Random Forest model
rf_model = RandomForestClassifier(n_estimators=100, random_state=42)
# Train the model
rf_model.fit(X_train, y_train)
print("Random Forest model trained successfully!")

# Step 3: Predict labels for new data points.
# Predict the species for the test set
predictions = rf_model.predict(X_test)

# Print the first few predictions
print("Predicted labels:", predictions[:5])
print("True labels:", y_test[:5])

# Step 4: Apply K-means Clustering**
# Calculate accuracy
accuracy = accuracy_score(y_test, predictions)
print(f"Accuracy: {accuracy:.2f}")

# Generate a confusion matrix
conf_matrix = confusion_matrix(y_test, predictions)
print("Confusion Matrix:")
print(conf_matrix)

# Plot the confusion matrix as a heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(conf_matrix, annot=True, fmt='d', cmap='Blues', xticklabels=set(target), yticklabels=set(target))
# Rotate the y-axis labels to horizontal
plt.yticks(rotation=0)
plt.title('Confusion Matrix')
plt.xlabel('Predicted Label')
plt.ylabel('True Label')
plt.show()

#------------------------------
```

    Training samples: 5756
    Testing samples: 1439
    Random Forest model trained successfully!
    Predicted labels: ['AdenomeraHylaedactylus' 'HypsiboasCinerascens' 'HypsiboasCordobae'
     'AdenomeraHylaedactylus' 'AdenomeraHylaedactylus']
    True labels: 3340    AdenomeraHylaedactylus
    5108      HypsiboasCinerascens
    6524         HypsiboasCordobae
    3649    AdenomeraHylaedactylus
    1617    AdenomeraHylaedactylus
    Name: Species, dtype: object
    Accuracy: 0.98
    Confusion Matrix:
    [[143   0   1   1   1   0   0   0   0   0]
     [  0 693   0   0   0   1   0   0   0   0]
     [  0   0 105   0   0   1   0   0   0   0]
     [  1   4   0  51   0   0   0   0   0   1]
     [  1   0   0   0  89   0   0   0   0   0]
     [  0   0   0   0   0 229   2   0   0   0]
     [  1   0   0   0   0   0  53   0   0   0]
     [  0   0   0   0   3   2   1  14   0   0]
     [  0   0   0   0   0   0   2   0  15   0]
     [  0   0   0   0   0   0   0   0   0  24]]

![png](output_41_1.png)

## ⚙️ What We Did

> 🟦 **In this practical, we:**
>
> - Introduced the core idea of **machine learning** as a way for computers to learn patterns from data
> - Distinguished between:
>   - **Features** (inputs)
>   - **Targets / labels** (outputs we want to predict)
> - Used a real dataset to explore how machine learning models are trained
> - Split data into **training** and **testing** sets
> - Introduced **supervised learning**, where the correct answers are known
> - Trained a simple machine learning model using **scikit-learn**
> - Used the trained model to make **predictions** on unseen data
> - Compared predictions to true values to assess performance
>
> 🧠 *The focus was on understanding the machine learning workflow: data → model → training → prediction → evaluation.*

---

## 📝 Exercises

> 🟦 **Exercise 1: Exploring the dataset**
>
> - Loaded and inspected the dataset used for machine learning
> - Identified which columns represent features and which represent the target
> - Checked data shape and basic statistics
>
> 🧠 *Goal: understand what information the model will learn from.*

---

> 🟦 **Exercise 2: Splitting data into training and testing sets**
>
> - Divided the dataset into a training set and a test set
> - Discussed why models should be evaluated on data they have not seen before
>
> 🧠 *Goal: learn how to fairly test a machine learning model.*

---

> 🟦 **Exercise 3: Training a machine learning model**
>
> - Created a machine learning model using scikit-learn
> - Trained the model using the training data
> - Examined how the model learns relationships between inputs and outputs
>
> 🧠 *Goal: see how a model is fitted automatically from data.*

---

> 🟦 **Exercise 4: Making predictions**
>
> - Used the trained model to make predictions on the test data
> - Compared predicted values to the true target values
>
> 🧠 *Goal: understand what it means for a model to “predict” unseen data.*

---

> 🟦 **Exercise 5: Evaluating model performance**
>
> - Calculated simple performance metrics (e.g. accuracy or error)
> - Reflected on how well the model performs
> - Discussed limitations and possible improvements
>
> 🧠 *Goal: recognise that machine learning models must be evaluated critically, not just run once.*

```python

```
