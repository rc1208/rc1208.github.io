---
layout: notebook
title:  "Introduction-to-Python"


---
```python
__author__ = "Rahul Chowdhury"
import sys
print(sys.version) # Using python 3.6 and custom Anaconda environment.
```

    3.6.5 |Anaconda custom (64-bit)| (default, Apr 26 2018, 08:42:37)
    [GCC 4.2.1 Compatible Clang 4.0.1 (tags/RELEASE_401/final)]


### Helpful links
1. To learn more how to setting up enivornments using Anaconda:  [Setting up a Conda Environment](https://conda.io/docs/user-guide/tasks/manage-environments.html) <br>
2. Great article showing why you should set up a python environment: [click here](https://medium.freecodecamp.org/why-you-need-python-environments-and-how-to-manage-them-with-conda-85f155f4353c)
3. Install Python package manager called [pip](www.https://pip.pypa.io/en/stable)
4. A very nice article to learn how to make pretty plots in matplotlib: [click here](https://www.datascience.com/learn-data-science/tutorials/creating-data-visualizations-matplotlib-data-science-python)

Let's start like how every coding tutorial begins. A "Hello World" in Python!


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
Let's explore some of the existing functions in Python. Note: For some of the functions, you may need to import the corresponding library. You can do that by using - *import* library_name


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

But, what if you need to make a custom function for your own needs. Maybe you want to add two numbers, break down a string or a function called TrickorTreat that generates candies? Let's generate that function because everyone wants candies!


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


![png](/images/2018-11-03-Introduction-to-Python_18_0.png)
