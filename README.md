# Scatter Chart Matplotlib
In this tutorial, we would like to create scatter charts using Python's Matplotlib.


### Prepare the matplotlib library.

This tutorial is using Python version 3.8, as a very stable version. With a ready python on your computer, check the following commands:

> python3 --version

> pip3 --version

> pip3 install matplotlib


Create a .py file, import the library, and you can also check the version of the matplotlib library as follows:
```
import matplotlib                # first step is to import the library
print(matplotlib.__version__)    # let's first check the version used
```

The pyplot is a submodule we will use where most of the Matplotlib utilities exist

```
import matplotlib.pyplot as plt  # let's import such submodule with an alias of plt
```



### Part 1: Let's create a simple scatter chart

With Pyplot, you can use the scatter() function to draw scatter charts, one dot representing a data point. The scatter() function accepts two equal-sized arrays: one for the values of the x-axis and one for the corresponding values on the y-axis (e.g., X-axis may represent the country number, and y-axis may represent the population).

```
import matplotlib.pyplot as plt

xValues = [9,6,8,6,2,17,3,9,5,12,13,9,6, 2, 17, 8]
yValues = [90,84,82,85,118,82,120,80,97,70,72,63,79, 80, 43, 51]

plt.scatter(xValues, yValues)
plt.show()
```


### Part 2: Creating multiple scatter charts in the same diagram

```
import matplotlib.pyplot as plt

xValues1 = [9,6,8,6,2,17,3,9,5,12,13,9,6, 2, 17, 8]
yValues1 = [90,84,82,85,118,82,120,80,97,70,72,63,79, 80, 43, 51]
plt.scatter(xValues1, yValues1)

xValues2 = [6, 3, 9, 7, 11, 4, 7, 11, 4, 5, 6, 8, 11, 5, 10]
yValues2 = [82, 91, 102, 84, 104, 93, 103, 74, 108, 96, 73, 76, 95, 82, 71]
plt.scatter(xValues2, yValues2)

plt.show()
```


### Part 3: Adding more style and format for the scatter chart

+ You can apply one color to the chart
```
plt.scatter(xValues, yValues, c = 'green')
plt.show()
```

+ You can also assign a color per point
```
designedColors = ["red","pink", ...... ,"yellow"]
plt.scatter(xValues, yValues, c=designedColors)
plt.show()
```

+ You can also consider the ColorMap (cmap) option to assign colors to the points. A colormap is a list of colors with a value ranging from 0 to 100. There is a wide range of colormap available to use (e.g., the 'gist_heat' colormap starts from 0 (with dark red) to 100 (with white)). In addition, you can also display the colormap using the colorbar() function

```
import matplotlib.pyplot as plt

xValues = [6, 3, 9, 7, 11, 4, 7, 11, 4, 5, 6, 8, 11, 5, 10]
yValues = [82, 91, 102, 84, 104, 93, 103, 74, 108, 96, 73, 76, 95, 82, 71]
designColors = [0, 10, 20, 30, 40, 45, 50, 55, 60, 70, 80, 90, 95, 40, 50]

plt.scatter(xValues, yValues, c=designColors, cmap='gist_heat')
plt.colorbar()
plt.show()
```

+ You can also control the size of the dot through the "s" parameter

```
import matplotlib.pyplot as plt

xValues = [6, 3, 9, 7, 11, 4, 7, 11, 4, 5, 6, 8, 11, 5, 10]
yValues = [82, 91, 102, 84, 104, 93, 103, 74, 108, 96, 73, 76, 95, 82, 71]
designColors = [0, 10, 20, 30, 40, 45, 50, 55, 60, 70, 80, 90, 95, 40, 50]
designSizes = [35,60,75,200,140,350,65,80,100,190,280,230,75,30, 250]

plt.scatter(xValues, yValues, c=designColors, cmap='gist_heat', s= designSizes)
plt.colorbar()
plt.show()
```


+ You can adjust the transparency of the dots through the "alpha" parameter
```
plt.scatter(xValues, yValues, c=designColors, cmap='gist_heat', s= designSizes, alpha=0.5)
plt.colorbar()
plt.show()
```
