---
layout: simple
title:  "Introduction-to-Python-new"


---
# Introduction to Python
```python
__author__ = "Rahul Chowdhury"
import sys
print(sys.version) # Using python 3.6 and custom Anaconda environment.
```

    3.6.5 |Anaconda custom (64-bit)| (default, Apr 26 2018, 08:42:37) 
    [GCC 4.2.1 Compatible Clang 4.0.1 (tags/RELEASE_401/final)]


 ## Helpful links 
1. To learn more how to setting up enivornments using Anaconda:  [Setting up a Conda Environment](https://conda.io/docs/user-guide/tasks/manage-environments.html) <br>
2. Great article showing why you should set up a python environment: [click here](https://medium.freecodecamp.org/why-you-need-python-environments-and-how-to-manage-them-with-conda-85f155f4353c)
3. Install Python package manager called [pip](www.https://pip.pypa.io/en/stable)
4. A very nice article to learn how to make pretty plots in matplotlib: [click here](https://www.datascience.com/learn-data-science/tutorials/creating-data-visualizations-matplotlib-data-science-python) 

*Let's start like how every coding tutorial begins. A "Hello World" in Python!*


```python
print("Hello World!") 
```

    Hello World!


**Tip #1:** If you are using Jupyter notebook, you can run every cell by hitting Enter + Shift button

### Variables in Python


```python
a = 1 #int
b = 1.1 #float
c = "Rahul" #string
d = [1,4,9,16] #list
e = True #boolean
f = {"Dog":1,"Cat":0} #dictionary
```

### In Built Functions in Python <br>
*Let's explore some of the existing functions in Python. Note: For some of the functions, you may need to import the corresponding library. You can do that by using - *import* library_name


```python
abs(-10) #returns the absolute value
```




    10




```python
max(d) #returns max from 'd' list defined above
```




    16




```python
age = dict([('Rahul', 24), ('Bob', 50)]) # Another way: age = {'Rahul':24, 'Bob': 50}
age

```




    {'Rahul': 24, 'Bob': 50}



### User Defined Functions in Python

*But, what if you need to make a custom function for your own needs. Maybe you want to add two numbers, break down a string or a function called TrickorTreat that generates candies? Let's generate that function because everyone wants candies!*


```python
import random #library for a generating a random number

def TrickorTreat():
    return random.randint(0,100) #generate number of candies from 0 to 100

print("You got", TrickorTreat(), "candies!")
```

    You got 45 candies!


### Basic Plotting using Matlpotlib


```python
import matplotlib.pyplot as plt
import numpy as np #library for creating neat scientific computing
# and helpful data structures such as  multidimensional arrays and matrices
#so that plots are inline in a Jupyter notebook
%matplotlib inline 
```


```python
# Set some parameters to apply to all plots. These can be overridden
# in each plot if desired
import matplotlib
# Plot size to 14" x 7"
matplotlib.rc('figure', figsize = (12, 6))
# Font size to 14
matplotlib.rc('font', size = 14)
# Add grid lines
matplotlib.rc('axes', grid = True)
# Set backgound color to white
matplotlib.rc('axes', facecolor = 'white')

```


```python
x = np.arange(0,100,1) #create an array from 0 to 100 with step size 1
y = [i*i for i in range(0,100)] #list having square of numbers from 0 to 100
```


```python
plt.plot(x, y, color='#E96F6C', linewidth=2)
plt.xlabel("Numbers")
plt.ylabel("Squares")
plt.title("Numbers Vs. Squares")
plt.show() #A plot to visualize the relation between numbers and their respective squares
```


![png](/images/2018-11-17-Introduction-to-Python_18_0.png)


### Basic Data Manipulation using Pandas

**Tip #2:** We are going to use Pandas library in Python. Pandas is software library written for the Python programming language for data manipulation and analysis.Pandas has been always been my go-to library for playing around with data in Pandas data structures called DataFrames.

#### Dataset
We are going to use a Kaggle dataset called 120 years of olympic history containing basic bio data on athletes and medal results from Athens 1896 to Rio 2016. Click here to download: [basic bio data on athletes and medal results from Athens 1896 to Rio 2016](https://www.kaggle.com/heesoo37/120-years-of-olympic-history-athletes-and-results)


```python
import pandas as pd #import the pandas library
data = pd.read_csv("120-years-of-olympic-history-athletes-and-results/athlete_events.csv") #read the csv file
```


```python
data.head(10) #Let's print the first 10 rows of the dataset
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
      <th>ID</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>A Dijiang</td>
      <td>M</td>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>A Lamusi</td>
      <td>M</td>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2012 Summer</td>
      <td>2012</td>
      <td>Summer</td>
      <td>London</td>
      <td>Judo</td>
      <td>Judo Men's Extra-Lightweight</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Gunnar Nielsen Aaby</td>
      <td>M</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>DEN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>21.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1988 Winter</td>
      <td>1988</td>
      <td>Winter</td>
      <td>Calgary</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>21.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1988 Winter</td>
      <td>1988</td>
      <td>Winter</td>
      <td>Calgary</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 1,000 metres</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>25.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1992 Winter</td>
      <td>1992</td>
      <td>Winter</td>
      <td>Albertville</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>25.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1992 Winter</td>
      <td>1992</td>
      <td>Winter</td>
      <td>Albertville</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 1,000 metres</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>27.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1994 Winter</td>
      <td>1994</td>
      <td>Winter</td>
      <td>Lillehammer</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 500 metres</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>9</th>
      <td>5</td>
      <td>Christine Jacoba Aaftink</td>
      <td>F</td>
      <td>27.0</td>
      <td>185.0</td>
      <td>82.0</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1994 Winter</td>
      <td>1994</td>
      <td>Winter</td>
      <td>Lillehammer</td>
      <td>Speed Skating</td>
      <td>Speed Skating Women's 1,000 metres</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
data.shape #tells us the structure of the dataset. For us, there are 271116 rows and 15 columns
```




    (271116, 15)




```python
data.info() #lists all the columns
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 271116 entries, 0 to 271115
    Data columns (total 15 columns):
    ID        271116 non-null int64
    Name      271116 non-null object
    Sex       271116 non-null object
    Age       261642 non-null float64
    Height    210945 non-null float64
    Weight    208241 non-null float64
    Team      271116 non-null object
    NOC       271116 non-null object
    Games     271116 non-null object
    Year      271116 non-null int64
    Season    271116 non-null object
    City      271116 non-null object
    Sport     271116 non-null object
    Event     271116 non-null object
    Medal     39783 non-null object
    dtypes: float64(3), int64(2), object(10)
    memory usage: 31.0+ MB



```python
data.describe() 
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
      <th>ID</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>271116.000000</td>
      <td>261642.000000</td>
      <td>210945.000000</td>
      <td>208241.000000</td>
      <td>271116.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>68248.954396</td>
      <td>25.556898</td>
      <td>175.338970</td>
      <td>70.702393</td>
      <td>1978.378480</td>
    </tr>
    <tr>
      <th>std</th>
      <td>39022.286345</td>
      <td>6.393561</td>
      <td>10.518462</td>
      <td>14.348020</td>
      <td>29.877632</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>10.000000</td>
      <td>127.000000</td>
      <td>25.000000</td>
      <td>1896.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>34643.000000</td>
      <td>21.000000</td>
      <td>168.000000</td>
      <td>60.000000</td>
      <td>1960.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>68205.000000</td>
      <td>24.000000</td>
      <td>175.000000</td>
      <td>70.000000</td>
      <td>1988.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>102097.250000</td>
      <td>28.000000</td>
      <td>183.000000</td>
      <td>79.000000</td>
      <td>2002.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>135571.000000</td>
      <td>97.000000</td>
      <td>226.000000</td>
      <td>214.000000</td>
      <td>2016.000000</td>
    </tr>
  </tbody>
</table>
</div>



**Tip #3:** A lot of times while dealing with datasets, there would be a lot of NA values. It is essential we deal with these values accordingly. Let's see how many NA values we have in our dataset.



```python
data.isnull().sum() #check for the number of NaN values 
```




    ID             0
    Name           0
    Sex            0
    Age         9474
    Height     60171
    Weight     62875
    Team           0
    NOC            0
    Games          0
    Year           0
    Season         0
    City           0
    Sport          0
    Event          0
    Medal     231333
    dtype: int64



*As we can see, the 'Age' column has 9474 NA values, 'Height' column has 60171 NA values, 'Weight' column has 62875 NA values. There techiniques in data mining which deal with NA valeus in a better way such as replacing the NA values with the mean of the attribute. Let's drop the rows for which 'Age' column is NA and then replace the NA values in 'Height' and 'Weight' column with the mean values of the respective columns*


```python
data.dropna(subset = ['Age'], inplace = True) #dropping the rows in where 'Age' == NA
#the inplace = True makes sure that the changes are reflected to the original dataframe

```


```python
data.isnull().sum() #there are zero NA 'age' values
```




    ID             0
    Name           0
    Sex            0
    Age            0
    Height     51574
    Weight     54263
    Team           0
    NOC            0
    Games          0
    Year           0
    Season         0
    City           0
    Sport          0
    Event          0
    Medal     222591
    dtype: int64




```python
data['Height'].fillna(data['Height'].mean(), inplace = True) #replace with avg. height
data['Weight'].fillna(data['Height'].mean(), inplace = True) #replace with avg. weight
```


```python
data.isnull().sum() #there are zero NA values in the dataset now
```




    ID             0
    Name           0
    Sex            0
    Age            0
    Height         0
    Weight         0
    Team           0
    NOC            0
    Games          0
    Year           0
    Season         0
    City           0
    Sport          0
    Event          0
    Medal     222591
    dtype: int64




```python
import seaborn as sns 
sns.set()
# Disable warnings in Anaconda
import warnings
warnings.filterwarnings('ignore')
```


```python
sns.distplot(data['Height'])

```




    <matplotlib.axes._subplots.AxesSubplot at 0x1a236623c8>




![png](/images/2018-11-17-Introduction-to-Python_35_1.png)



```python
sns.distplot(data['Weight'])
```




    <matplotlib.axes._subplots.AxesSubplot at 0x10b17d780>




![png](/images/2018-11-17-Introduction-to-Python_36_1.png)



```python
sns.jointplot(x='Height', y='Weight', data=data, kind='scatter');
```


![png](/images/2018-11-17-Introduction-to-Python_37_0.png)

