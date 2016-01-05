# Python graphics: Matplotlib fundamentals 

---
**Overview.**  We introduce and apply Python's popular graphics package, Matplotlib.  

**Python tools.**  Graphing with Matplotlib.

**Buzzwords.** Packages (libraries, modules), data visualization.  

**Applications.**  Incomes of college majors.??

**Code.** [Link](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/IPython/bootcamp_graphics_1.ipynb).

---


Computer graphics are one of the great advances of the modern world.  Graphs have always been helpful in describing data or concepts, but they're a lot easier to produce now than they were a few years ago. In fact, we've gotten so good at drawing pictures that we invented a new term for it:  **visualization**.  

That's the good news.  The bad news, or at least the reigning fact of life, is that graphics are inherently complicated.  Programs like Excel do their best to hide this fact, but if you ever try to customize a chart it quickly rears its ugly head.  Have you ever spent a couple hours trying to fine-tune an Excel graph?  More?  The problem is that even simple graphs have lots of moving parts:  the type (line, bar, etc); the color and thickness of lines, bars, or markers; title and axis labels; their location, fonts, and font sizes; tick marks (location, size); background color; grid lines (on or off); and so on.  So there's a lot of stuff to keep track of.  

We introduce graphics with **Matplotlib**, Python's leading graphics package.  We show how to put it to work and make a start on producing effective -- and attractive -- visualizations.  

One more thing:  Download the IPython notebook at the Code link.  Remember to click on the Raw button to get the real file.  

## Reminders 

* Packages.  Collections of tools that extend Python's capabalities. We add them with `import` statements.  

* Pandas.  Python's data management package.  We typically add it to our programs with 
```python
import pandas as pd 
```

* Dataframe.  A data structure like a spreadsheet that includes a table of data plus row and column labels.  Typically columns are variables and rows are observations.  Common dataframe methods include `columns` (column labels), `index` (row labels), and `plot` (graph the columns).  

* Series.  A single variable `x` in a dataframe `df` can be expressed as the series `df['x']`.  

* Reading spreadsheets.  We can "read" data into Python using the `read_csv` and `read_excel` functions in Pandas. 

* API.  Or we can use the APIs for FRED, the World Bank, Fama-French, and other data sources.  

* Jupyter.  A Python environment in which we create IPython notebooks.  These notebooks combine Python code with text and output, including graphics. 


## IPython notebooks in Jupyter

We're going to change environments from Spyder to Jupyter and work with IPython notebooks. We had a brief confrontation with Jupyter when we installed Anaconda, but that was in the distant past.  We give a quick introduction now and rely on constant use over the coming weeks to get us up to speed.


**Creating an IPython notebook.** We can open a new IPython notebook by tracing the steps we took in the first class:   

* Start the Anaconda Launcher.  
* Click on ipython-notbook to launch Jupyter.  This will open a tab in your browser with the word Jupyter at the top and your computer's directory structure below it.  
* In the browser tab, navigate to your `Data_Bootcamp` directory/folder.  
* Click on the New button in the upper right and choose Python 3.  

You now have a new empty Python notebook we can use to play around with.  If you have a few minutes, click on help in the menubar at the top and choose User Interface Tour.  


**Jupyter essentials.**  In your browser, you should have an empty notebook with the word Jupyter at the top.  Below it is a "menubar" with the words File, Edit, View, Cell, Kernel, and Help.  Below that is a "toolbar" with various buttons.  

Let's put some of these tools to work:  

* Change the notebook name.  Click on the name (usually `Untitled`) to the right of the word Jupyter at the top. A textbox should open up.  Use it to change the name to "[your name]'s sandbox".

* Toobar buttons.  Run your mouse over one of them to see what it does.  

* Add a cell.  Click on the `+` in the toolbar to create a new cell.  Choose Code in the dropdown menu in the toolbar and add this code:  
```python
import datetime 
print('Welcome to Data Bootcamp!')
print('Today is: ', datetime.date.today())
```
Now click on Cell in the menubar and choose Run cell.  What do you see?  

* Add another cell.  Click on the `+` to create another cell and choose Markdown in the dropdown menu in the menubar.  Markdown is a kind of text; more shortly.  Type in the cell:  
```
Your name 
Data Bootcamp sandbox for playing around with IPython notebooks 
```

You get the idea.  To get a sense of what's possible, take a look at these [two](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/IPython/bootcamp_test.ipynb) [notebooks](http://nbviewer.ipython.org/github/justmarkham/DAT4/blob/master/notebooks/08_linear_regression.ipynb).  


**Markdown essentials.**  Markdown is a simplified verson of html ("hypertext markup language"), the language used to construct basic websites.  html was a great thing in 1990, but most of us find it painfully cumbersome to work with.  Markdown is a lot easier.  Here are some things we can do with it:  

* Headings.  Large bold headings are marked by hashes (`#`).  One hash for first level (very large), two for second level, three for third level, four for fourth.  We tend to use three hashes because the others are too big.  Tey these in a markdown cell and see what you think:  
```
# Data Bootcamp sandbox 
## Data Bootcamp sandbox 
### Data Bootcamp sandbox 
```
* Bold and italics.  If we put a word between two pairs of double asterisks, it's displayed in bold.  Thus `**bold**` is displayed as **bold**.  If we use single quotes, we get italics:  `*italics*` displays as *italics*.  

* Links.   We construct a link with the text in square brackets and the url in parentheses immediately afterwards.  Try this one:  
```
[Data Bootcamp course](http://databootcamp.nyuecon.com/)
```

You can find more information about Markdown under Help.  Or use your Google fu.  

**Exercise.** Create a description cell in Markdown at the top of your notebook.  It should mention the Data Bootcamp course, your name, and a description of what you're doing in the notebook.  Extra credit:  Add a link.  


## Three approaches to graphics 

Ok, now back to  graphics.  Python's leading graphics package is Matplotlib.  Matplotlib can be used in a number of different ways:  

* Approach #1:  Plot methods.  Apply a plot-like method to a dataframe.   
* Approach #2:  `plot(x,y)`.  Basic function for plotting y against x.  
* Approach #3:  Figure objects.  Create figure objects, apply methods to them.  

All three call on the same functionality, but they use different syntax. 



## Getting started 


**Data sets.**

We'll go through all three in an IPython notebook, linked at the top.  The examples below us


**IPython help.** 

??


##  Approach #1:  Apply plot method to data 

This is the easiest, perfect for simple graphs.  

Special methods for dataframes...  One advantage is that ... 

What is the x axis here?  

plot, bar, barh, scatter ...


## Approach #2:  `plot(x,y)`




## Approach #3:  Apply methods to figure objects 




## Approach #1 revisited 

Create fig... 





## Links 

Viz of the Day
Tableau
Viz Wiz

Graphic Detail*


Heatmaps:  http://stackoverflow.com/questions/14391959/heatmap-in-matplotlib-with-pcolor 


## Resources 

Matplotlib 

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
