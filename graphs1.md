# Python graphics: Matplotlib fundamentals 

---
**Overview.**  We introduce and apply Python's popular graphics package, Matplotlib.  

**Python tools.**  Graphing with Matplotlib.

**Buzzwords.** Packages (libraries, modules), data visualization.  

**Applications.**  Incomes of college majors.??

**Code.** [Link](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/bootcamp_graphics_1.py).

---


Computer graphics are one of the great advances of the modern world.  Graphs have always been helpful in describing data or concepts, but they're a lot easier to produce now than they were a few years ago. In fact, we've gotten so good at drawing pictures that we invented a new term for it:  **visualization**.  

That's the good news.  The bad news, or at least the reigning fact of life, is that graphics are inherently complicated.  Programs like Excel do their best to hide this fact, but if you ever try to customize a chart it quickly rears its ugly head.  Have you ever spent a couple hours trying to fine-tune an Excel graph?  More?  The problem is that even simple graphs have lots of moving parts:  the type (line, bar, etc); the color and thickness of lines, bars, or markers; title and axis labels; their location, fonts, and font sizes; tick marks (location, size); background color; grid lines (on or off); and so on.  So there's a lot of stuff to keep track of.  

We introduce graphics with **Matplotlib**, Python's leading graphics package.  We show how to put it to work and make a start on producing effective -- and attractive -- visualizations.  


## Reminders 

* Packages.  Collections of tools that extend Python's capabalities. We add them with `import` statements.  

* Pandas.  Python's data management package.  We typically add it to our programs with 
```python
import pandas as pd 
```

* Dataframe.  A data structure like a spreadsheet that includes a table of data plus row and column labels.  Typically columns are variables and rows are observations.  Common dataframe methods include `columns` (column labels), `index` (row labels), and `plot` (graph the columns).  

* Series.  A single variable.  A variable `x` in a dataframe `df` can be expressed as the series `df['x']`.  

* Reading spreadsheets.  We can "read" data into Python using the `read_csv` and `read_excel` functions in Pandas. 

* API.  Or we can use the APIs for FRED, the World Bank, Fama-French, nd other data sources.  

* Jupyter.  A Python environment in which we create IPython notebooks.  These notebooks ombine Python code with text and output, including graphics. 


## IPython notebooks in Jupyter

We're going to change environments here to Jupyter and work with IPython notebooks.  


## Jupyter basics 

What it looks like...  

Markdown.  

* hashes for headings..

* **bold** 

Code...  


Magics.. 

* maplotlib inline 





## Three approaches to graphs 

Matplotlib has a number of approaches ...

* Approach #1:  Plot methods.  Apply a plot-like method to a dataframe or other data.   

* Approach #2:  `plot(x,y)`.  Basic function for plotting y against x.  

* Approach #3:  create figure objects, apply methods to them.  

All three call on the same functionality, but they use different syntax. 


##  Approach #1:  Apply plot method to data 

This is the easiest, perfect for simple graphs.  

Special methods for dataframes...  One advantage is that ... 


plot, bar, barh, scatter ...


## Approach #2:  `plot(x,y)`




## Approach #3:  apply methods to figure objects 






## Style sheets 

```python 
import matplotlib.pyplot as plt

# http://matplotlib.org/users/style_sheets.html
plt.style.use('ggplot')
plt.style.reload_library()  # does this reset default?  
```


Revert to defaults:  http://stackoverflow.com/questions/26413185/how-to-recover-matplotlib-defaults-after-setting-stylesheet

import matplotlib as mpl
mpl.rcParams.update(mpl.rcParamsDefault)

Also saw this:   plt.rcdefaults() 



## Examples 

http://fivethirtyeight.com/datalab/the-extreme-economic-outlier-that-is-greece-in-7-charts/

Chetty 100 x 100 heatmap?
http://www.equality-of-opportunity.org/images/online_data_tables.xls 


xkcd-style graphs 

great example of documenting code:  https://jakevdp.github.io/blog/2012/10/07/xkcd-style-plots-in-matplotlib/
http://jakevdp.github.io/blog/2013/07/10/XKCD-plots-in-matplotlib/

http://matplotlib.org/examples/showcase/xkcd.html

fonts:  http://stackoverflow.com/questions/19663986/getting-xkcd-plots-using-matplotlib



## Links 

Viz of the Day
Tableau
Viz Wiz

Graphic Detail*


Heatmaps:  http://stackoverflow.com/questions/14391959/heatmap-in-matplotlib-with-pcolor 


## Resources 

Matplotlib 

* Matplotlib's [Pyplot tutorial](http://matplotlib.org/users/pyplot_tutorial.html) is excellent. 

* Matplotlib's [gallery of examples](http://matplotlib.org/gallery.html) is also a great starting point.  Find an example you like, download the code, and adapt it to your needs.   

* Another gallery:  https://www.getdatajoy.com/examples/python-plots 

* Rougier, Mueller, and Varoquaux's [SciPy lecture notes](https://scipy-lectures.github.io/intro/matplotlib/matplotlib.html) are also quite good.  It's aimed at scientists, so the examples tend to be mathematical.  Their [cookbook](http://wiki.scipy.org/Cookbook/Matplotlib) has a good collection of samples.  

* http://nbviewer.ipython.org/github/jrjohansson/scientific-python-lectures/blob/master/Lecture-4-Matplotlib.ipynb 

* Sargent and Stachurski's [Quantitative Economics](http://quant-econ.net/) has a good overview of Matplotlib, but we find it a little terse.  

* [Practical business Python](http://pbpython.com/visualization-tools-1.html) is a terrific blog.  This post concerns Python visualization packages.  He likes Seaborn.  

https://github.com/rasbt/matplotlib-gallery 

Check this out:  Benjamin Root and Joe Kington, SciPy 2015.
https://youtu.be/MKucn8NtVeI
https://github.com/WeatherGod/AnatomyOfMatplotlib

Colormap:  https://www.youtube.com/watch?v=xAoljeRJ3lU .  Sort of interesting, moderately technical, short.  

http://nbviewer.ipython.org/gist/msund/11349097
https://www.reddit.com/r/Python/comments/2cfulw/indepth_matplotlib_tutorials_beginner_to_advanced/ 
http://pythonprogramming.net/matplotlib-graphing-series/


https://conference.scipy.org/scipy2013/tutorial_detail.php?id=103

Jake:  https://vimeo.com/53057312
http://jakevdp.github.io/mpl_tutorial/ 

Tufte interview:  http://adage.com/article/adagestat/edward-tufte-adagestat-q-a/230884/
