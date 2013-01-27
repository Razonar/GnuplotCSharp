Gnuplot.C#
========

Overview
--------
Most scientific publications with graphs use gnuplot.  It is extremely well documented and handles 2D, 3D (surface and pointcloud), heatmap, png, jpg, and much more using simple math syntax as well as simple text-based data.  And it supports many output formats, as well interactive zooming/rotating.

It only takes about 10 lines of code to wire up C# to send commands to gnuplot.  But as soon as you try to send arrays of data, overlay multiple graphs, and generally work with gnuplot from C#, you'll immediately see that you have to add all kinds of utility functions to not clutter up your code.

Gnuplot.C# provides a nice set of functions to make it easy to use all the power of gnuplot to visualize your data in C#.  Check out the examples of how easy it is to visualize functions and data.

Installation
----------
Just put gnuplot.cs in your project, change the first line from C:\gnuplot\bin to the location of gnuplot.exe on your system.  

If you haven't installed gnuplot on your system, download it at http://sourceforge.net/projects/gnuplot/files/ or http://www.gnuplot.info 

Inspiration
-----------
In 2012, I completed the excellent Machine Learning course by Andrew Ng (Coursera).  We used Octave/Matlab, and Octave uses gnuplot for its graphs. I wanted to recreate all the class projects in C# for practice.  Microsoft has a cloud numerics library, so C# is a good choice for machine learning if you want to for example, train your machine learning algorithm on a large dataset and scale across many computers in the Azure cloud.

I believe this project will be helpful to anyone who wants to visualize data/functions in C#, so I have released it here.

Examples
========
To see various demos in action, download the files, open the solution (Visual Studio) and run Demo.cs (make sure you've installed gnuplot first)

If you are not familiar with gnuplot, I recommend you visit www.gnuplot.info and see all the demos there.  Then come back for how to do it all in C#.

Plot
--------

Plot a function
```C#
GnuPlot.Plot("sin(x) + 2");
```
Output
![Plot a function](https://github.com/awokeknowing/readmeimages/plotf.png "Plot a function")

Plot a function with custom color and line width (see gnuplot documentation)
```C#
GnuPlot.Plot("sin(x) + 2", "lc rgb \"magenta\" lw 5");
```
Output

Plot an array of y values
```C#
double[] Y = new double[] { -4, 6.5, -2, 3, -8, -5, 11, 4, -5, 10 };
GnuPlot.Plot(Y);
```
Output


Plot an array of x and y values
```C#
double[] X = new double[] { -10, -8.5, -2, 1, 6, 9, 10, 14, 15, 19 };
double[] Y = new double[] { -4, 6.5, -2, 3, -8, -5, 11, 4, -5, 10 };
GnuPlot.Plot(X, Y);
```
Output


Overlay multiple graphs
```C#
GnuPlot.HoldOn();
GnuPlot.Plot("cos(x) + x");
GnuPlot.Plot("cos(2*x)", "with points pt 3");
```
Output


Splot  (3D data)
--------

plot a 3D function
```C#

```

plot a file with 3D data
```C#

```

plot an array of z values (specify y size to break the array into a square grid)
```C#

```

plot a grid of z values
```C#

```

plot a grid of x, y, and z values
```C#

```


Contour (3D data as "top view" with contour lines)
--------
Contour maps are very useful to make it easier to see the peaks and valleys, and see what areas have the same range of values.  Gnuplot lets you show contour maps, but you can't draw 2d points and lines on them.  The Contour methods generate a 2D contour map, allowing you to plot further data points on it.

```C#

```


Heatmap  (intensity/z-scale map)
--------

```C#

```

Set and Unset
--------

```C#

```

Replot
--------

```C#

```

Write and WriteLine
--------

```C#

```

SaveData
--------

```C#

```

PointStyles
--------

```C#

```

StoredPlot  
--------

```C#


```

API Reference
---
Plot

Splot

Contour

Heatmap

Set

Unset

HoldOn

HoldOff

SaveData

WriteLine

Write

Replot

License
-------
You are free to use this code as you wish.  Please mention you got it on GitHub from James Morris aka AwokeKnowing. Also, email me at james david morris a/t g mail .com (no spaces) and let me know about your project.

Disclaimer
----------
Use this code at your own risk.  The author cannot guarantee that it is free of defects or that it will not damage your system or corrupt your data.  It's less than 1000 lines of code, so just look at it, and decide if it works for you.

Happy coding!!