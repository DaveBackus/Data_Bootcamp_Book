# Python graphics: Matplotlib fundamentals 

---
**Overview.**  We introduce and apply Python's popular graphics package, Matplotlib.  

**Python tools.**  Graphing with Matplotlib: `plot()` methods with dataframes, `plot(x,y)`, and figure objects.

**Buzzwords.** Data visualization.  

**Applications.**  US GDP, GDP per capita in selected countries, 

**Code.** [Link](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/IPython/bootcamp_graphics_1.ipynb).

---


Computer graphics are one of the great advances of the modern world.  Graphs have always been helpful in describing data or concepts, but they're a lot easier to produce now than they were a few years ago. In fact, we've gotten so good at drawing pictures that we invented a new term for it:  **visualization**.  If done well, a good graph can tell us something new -- and get us thinking about related things we'd like to know.   

That's the good news.  The bad news is that graphics are inherently complicated.  Programs like Excel do their best to hide this fact, but if you ever try to customize a chart it quickly rears its ugly head.  Have you ever spent a couple hours trying to fine-tune an Excel graph?  More?  The problem is that even simple graphs have lots of moving parts:  the type (line, bar, scatter, etc); the color and thickness of lines, bars, or markers; title and axis labels; their location, fonts, and font sizes; tick marks (location, size); background color; grid lines (on or off); and so on.  So there's a lot of stuff to keep track of.  

Our goal here is to learn to produce graphs  with **Matplotlib**, Python's leading graphics package. Matplotlib can be used in several ways.  We show how they work and produce a few visualizations that we hope bring data to life.  There's a lot here, but don't panic, it gets easier with time.  

One more thing before we get started:  **Save the IPython notebook** at the Code link above in your `Data_Bootcamp` directory/folder.  The link goes to a display of the notebook, but you need to click on the Raw button to get the real file.  


## Reminders 

* Packages.  Collections of tools that extend Python's capabalities. We add them with `import` statements.  

* Pandas.  Python's data management package.  We typically add it to our programs with 
```python
import pandas as pd 
```

* Dataframe.  A data structure like a spreadsheet that includes a table of data plus row and column labels.  Typically columns are variables and rows are observations.  Common dataframe methods include `columns` (column labels), `index` (row labels), and `plot` (graph the columns).  

* Series.  A single variable `x` in a dataframe `df` can be expressed as the series `df['x']`.  

* Objects and methods.  Recall -- again! -- that we apply the method `justdoit` to the object `x` with `x.justdoit`.  An example we'll see repeatedly is the `plot()` method applied to the dataframe `df` with `df.plot()`.  

<!-- 


* Reading spreadsheets.  We can "read" data into Python using the `read_csv` and `read_excel` functions in Pandas. 

* API.  Or we can use the APIs for FRED, the World Bank, Fama-French, and other data sources.  
-->

* Jupyter.  A Python environment in which we create IPython notebooks.  These notebooks combine Python code with text and output, including graphics. It's the ideal medium for this topic.  


## IPython notebooks in Jupyter

We're going to change environments from Spyder to Jupyter and work with IPython notebooks. We had a brief introduction with Jupyter when we installed Anaconda, but we'll go through it again to make sure it sticks.  

**Creating an IPython notebook.** We can open a new IPython notebook by tracing the steps we took in the first class:   

* Start the Anaconda Launcher.  
* Click on ipython-notbook to launch Jupyter.  This will open a tab in your browser with the word Jupyter at the top and your computer's directory structure below it.  
* In the browser tab, navigate to your `Data_Bootcamp` directory/folder.  
* Click on the New button in the upper right and choose Python 3.  

We now have a new empty Python notebook we can use to play around with.  


**Jupyter essentials.**  In your browser, you should have an empty notebook with the word Jupyter at the top.  Below it is a **menubar** with the words File, Edit, View, Cell, Kernel, and Help.  Below that is a **toolbar** with various buttons.  If you have a few minutes, click on help in the menubar at the top and choose User Interface Tour.  

Let's put some of these tools to work:  

* Change the notebook name.  Click on the name (`Untitled` if we just created a new notebook) to the right of the word Jupyter at the top. A textbox should open up.  Use it to change the name to "[your name]'s sandbox".

* Toobar buttons.  Run your mouse over one of them to see what it does.  

* Add a cell.  Click on the `+` in the toolbar to create a new cell.  Choose Code in the toolbar's dropdown menu.  Type this code in the cell:  
```python
import datetime 
print('Welcome to Data Bootcamp!')
print('Today is: ', datetime.date.today())
```
Now click on Cell in the menubar and choose Run cell.  What do you see?  

* Add another cell.  Click on the `+` to create another cell and choose Markdown in the toolbar's dropdown menu. Markdown is text; more on it shortly.  Type this in the cell:  
```
Your name 
Data Bootcamp sandbox for playing around with IPython notebooks 
```
Run this cell as well.  

You get the idea.  To get a sense of what's possible, take a look at these [two](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/IPython/bootcamp_test.ipynb) [notebooks](http://nbviewer.ipython.org/github/justmarkham/DAT4/blob/master/notebooks/08_linear_regression.ipynb).  


**Markdown essentials.**  Markdown is a simplified verson of html ("hypertext markup language"), the language used to construct basic websites.  html was a great thing in 1990, but now that the excitement has warn off we find it painful.  Markdown, however, has a zen-like simplicity.  Here are some things we can do with it:  

* Headings.  Large bold headings are marked by hashes (`#`).  One hash for first level (very large), two for second level (a little smaller), three for third level (smaller still), four for fourth (the smallest).  Try these in a markdown cell to see how they look:  
```
# Data Bootcamp sandbox 
## Data Bootcamp sandbox 
### Data Bootcamp sandbox 
```
Be sure to run the cell when you're done.  
* Bold and italics.  If we put a word between two pairs of double asterisks, it's displayed in bold.  Thus `**bold**` is displayed as **bold**.  If we use single quotes, we get italics:  `*italics*` displays as *italics*.  

* Links.   We construct a link with the text in square brackets and the url in parentheses immediately afterwards.  Try this one:  
```
[Data Bootcamp course](http://databootcamp.nyuecon.com/)
```

You can find more information about Markdown under Help.  Or use your Google fu.  

Markdown is ubiquitous on the web.  This book, for example, is written in Markdown.  Click [here](https://github.com/DaveBackus/Data_Bootcamp_Book/blob/master/data-mentality.md) for a list of chapter files.  Click on one to see how it displays.  Click on the Raw button at the top to see the Markdown file that produced it.  

**Exercise.** Create a description cell in Markdown at the top of your notebook.  It should mention the Data Bootcamp course, your name, and a description of what you're doing in the notebook.  *Bonus points:*  Add a link.  


**IPython help.** We can access documentation just as we did in Spyder's IPython console:  type a function or method and ad a question mark.  For example:  `print?` or `df.plot?`.  


## Three approaches to graphics in Matplotlib

Ok, now back to  graphics.  Python's leading graphics package is **Matplotlib**.  Matplotlib can be used in a number of different ways:  

* Approach #1:  Plot methods.  Apply a plot-like method to a dataframe.   
* Approach #2:  `plot(x,y)`.  Basic function for plotting y against x.  
* Approach #3:  Figure objects.  Create figure objects, apply methods to them.  

All three call on the same functionality, but they use different syntax. We use all three at times but favor 1 and 3.  


We import Matplotlib abd its pyplot module (don't ask) with 
```python
import matplotlib as mpl
import matplotlib.pyplot as plt 
```
We also get access to Pandas dataframes with
```python
import pandas as pd 
```
All of these statements go at the top of our program.  


## Sample dataframes


We use three dataframes to to illustrate various approaches to Matplotlib graphics.  

**US GDP.** The first one is several years of US GDP and Consumption.  We got the numbers from FRED, but have written them out here for simplicity.  The code is 
```python
gdp  = [13271.1, 13773.5, 14234.2, 14613.8, 14873.7, 14830.4, 14418.7,
        14783.8, 15020.6, 15369.2, 15710.3]
pce  = [8867.6, 9208.2, 9531.8, 9821.7, 10041.6, 10007.2, 9847.0, 10036.3,
        10263.5, 10449.7, 10699.7]
year = [2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013]

us = pd.DataFrame({'gdp': gdp, 'pce': pce}, index=year) 
print(us)
```
Note that we created a dataframe from a dictionary.  That's convenient here, but in most real applications we'll read in spreadsheets or access APIs.  


**World Bank.** The second dataframe contains 2013 data for several countries.  This code is on an IPython cell:  
```python
code    = ['USA', 'FRA', 'JPN', 'CHN', 'IND', 'BRA', 'MEX']
country = ['United States', 'France', 'Japan', 'China', 'India',
             'Brazil', 'Mexico']
gdppc   = [53.1, 36.9, 36.3, 11.9, 5.4, 15.0, 16.5]

wb = pd.DataFrame({'gdppc': gdppc, 'country': country}, index=code)
wb
```
The last line -- the dataframe name `wb` on its own -- results in the display of `wb`.  That works as long as this is the last statement in the cell.  


**Fama-French returns.** The third dataframe reads in annual returns from Fama and French:
```python 
ff = web.DataReader('F-F_Research_Data_factors', 'famafrench')[1]
ff.columns = ['xsm', 'smb', 'hml', 'rf']
ff['rm'] = ff['xsm'] + ff['rf']
ff = ff[['rm', 'rf']]     # extract rm and rf (return on market, riskfree rate) 
ff.head(5)
```
This gives us a dataframe with two variables:  `rm` is the return on the equity market overall and `rf` is the riskfree return.  


**Exercise.** What kind of object is `us`?  How would you access its column and row labels?  What are they?  


## Digression:  Graphing in Excel 

Before charging ahead, let's review how we would create what Excel calls a "chart".  We need to choose:  

* Data.  Typically we would highlight a block in a spreadsheet.  Typical data would be in columns with labels at the top, much like a dataframe.  
* Chart type.  Lines, bars, scatter, and so on.  
* `x` and `y` variables.  Typically we graph some `y` variable -- or perhaps several of them -- against an `x` variable.  In the graph, `x` is measured on the horizontal axis and `y` is measured on the vertical axis. 

This might be followed by a long list of fine-tuning:  what the lines look like, how the axes are lebeled, and so on.  

We'll see the same things below.  


##  Approach #1:  Apply plot method to data 

The simplest way to produce graphics from a dataframe is to apply a method to it.  We like simple, and do this a lot.  

If we compare this to Excel, a number of things are preset for us:

* Data.  By default (meaning, if we don't do anything to change it) the data consists of the whole dataframe.  
* Chart type.  We'll see below that we have options for lines, bars, or other things.  
* `x` and `y` variables.  By default, the `x` variable is the dataframe's index and the `y` variables are all the columns of the dataframe.  

We can change all of these things, as we can in Excel, but that's the starting point.  


**Example (line plot).**  Enter the statement `us.plot()` into an IPython cell and run it.  This plots every column of the dataframe `us` as a line against the index, the year of the observation.  The lines have different colors; we didn't ask for this, it's built in.  A legend associates each variable name with a line color; this is also built in.  


**Example (bar chart).**  The statement `us.plot(kind='bar')` produces a bar chart of the same data. 


**Exercise.** Show that the statement `us.plot.bar()` produces the same output.  


**Exercise (scatterplot).** In a scatter plot, each point associates a variable `y` with another variable `x`.  Here we'll use `gdp` as `x` and `pce` (consumption) as `y`.  The general syntax for a dataframe `df` is `df.plot.scatter(x,y)`.  In this case we use 
```python
us.plot('gdp', 'pce', kind='scatter')
```

We have lots more choices.  Use the IPython help by typing `us.plot?` in an empty cell and running it. What parameters look interesting to you?  Add each of these arguments to `us.plot()`in the code cell below and describe what they do:  

* `kind='area'`
* `subplots=True`
* `sharey=True`
* `figsize=(3,6)`
* `xlim=(0, 16000)`


We can do the same thing with the Fama-French data.  The basic plot is 
```python 
ff.plot()
```
This one has one series (the equity market return `rm`) that varies a lot and one (the riskfree return `rf`) that does not.  

**Exercise.**  Let's see if we can dress this one up a little.  Try adding, one at a time, the arguments title='Fama-French returns' and legend=False. What does the documentation say about them? What do they do? 

We might see if we can describe the behavior of these returns in a more systematic way.  One option is a histogram:
```python 
ff.plot(kind='hist', bins=20, subplots=True)
```
We plot the two variables separately with 20 "bins" in each histogram.  


**Exercise.**  What does this graph tell us about the two returns?  


**Exercise.**  Use the World Bank dataframe `wb` to create a bar chart of GDP per capita. *Bonus points:* Create a horizontal bar chart. *Double bonus:* Add country name labels to it.



## Approach #2:  `plot(x,y)`

Next up:  the popular pyplot module of Matplotlib which we import with 
```python
import matplotlib.pyplot as plt
```
This is a more explicit version  of Matplotlib graphics in which we specify the `x` and `y` variables explicitly.  A typical statement has the form
```python
plt.plot(x, y)
```
We used pyplot a lot when we started out, and suspect you will, too.  We'll see the same figures as before, but we get there with different syntax.  


**Basic plots.** Compare these plots to our earlier ones.  We start with GDP on its own:  
```python 
plt.plot(us.index, us['gdp'])
```
Remind yourself what the `x` and `y` variables are.  If we want two variables in the same graph, we simply add another line:
```python 
plt.plot(us.index, us['gdp'])
plt.plot(us.index, us['pce'])
```
If we want a bar chart we use 
```python 
plt.bar(us.index, us['gdp'])
```
The bars here are off center, so we often include the argument `align='center'`.


**Exercise.** Experiment with 
```python
plt.bar(us.index, us['gdp'], 
		align='center', 
		alpha=0.65, 
		color='red', 
		edgecolor='green')
```
Describe what each of the arguments does. 


**Adding things to graphs.** We can add features to the graph with additional lines.  Consider these:
```python
plt.plot(us.index, us['gdp']) 
plt.title('US GDP', fontsize=16, loc='left')
plt.ylabel('Billions of 2009 USD')
plt.xlim(2002.5, 2013.5)
```
In this way we add a title at the top (16 point type and left justified), add a lable to the y axis, and change the limits of the x axis.  

**Exercise.** Add a `plt.ylim` statement to make the `y` axis start at zero, as it did in the bar charts.  *Bonus points:*  Change the color of the line to magenta and the linewidth to 2.  *Hint:*  Use `plt.plot?` to get the documentation.  


**Exercise.** For the Fama-French dataframe `ff`, create a line chart that includes both returns.  *Bonus points:* Add a title.  


## Approach #3:  Create figure objects and apply methods 

This approach is the most foreign to beginners, but now that we're used to it we like it a lot.  We either use it on its own, or adapt its functionality to the dataframe plot methods we saw in Approach #1.  The idea is to generate an object -- two objects, in fact -- and apply methods to them to produce the various elements of a graph:  the data, their axes, their labels, and so on.  


**Create objects.** This is how we do it:
```python
# create fig and ax objects
fig, ax = plt.subplots()
```
This produces a blank figure, which is displayed in IPython.  The names `fig` and `ax` can be anything, but these are standard.  We say `fig` is a **figure object** and `ax` is an **axis object**.  This means:
    
* `fig` is a blank canvas for creating a figure.  
* `ax` is everything in it:  axes, labels, lines or bars, and so on.  

We apply methods to both objects to create data graphs.  


**Create graphs.**  We create graphs by applying plot-like methods to `ax`.  This is an example that uses pyplot's `plot(x,y)` syntax:  
```python
ax.plot(us.index, us['gdp'], linewidth=2, color='magenta')
ax.set_title('US GDP', fontsize=14, loc='left')
ax.set_ylabel('Billions of USD')
```
The first line creates a line plot with the usual `plot(x,y)` syntax.  The next two lines add a title and y-axis label.  We have access to the usual set of methods for refining figures.  We can get a list using tab completion:  type `ax.[tab]` in an IPython code cell.  

We don't use fugure methods much, but here's one:  
```python 
# a figure method: save figure as a pdf 
fig.savefig('us_gdp.pdf')
```
This saves the figure as a pdf file.  


**Exercise.** Create a bar chart of variable `rm` in the `ff` dataframe.  *Bonus points:* Make the bars red.  


**Multiple plots.** 


```python
fig, ax = plt.subplots(nrows=2, ncols=1, sharex=True)

ax[0].plot(us.index, us['gdp'], color='green')   # first plot 
ax[1].plot(us.index, us['pce'], color='red')     # second plot 
```


**Approach #1 revisited.** 


## Reviewing the bidding



Not something we commit to memory.  Start with examples, old code.  


## Examples.  


**PISA test scores.** Recall that we had a simple plot, but it didn't look very good.  The code was 
```python 
import pandas as pd
url = 'http://dx.doi.org/10.1787/888932937035'
pisa = pd.read_excel(url, 
                     skiprows=18,       # skip the first 18 rows 
                     skipfooter=7,      # skip the last 7 
                     parse_cols=[0,1,9,13],   # select columns of interest 
                     index_col=0,       # set the index as the first column
                     header=[0,1]       # set the variable names 
                     )
pisa = pisa.dropna()                    # drop blank lines 
pisa.columns = ['Math', 'Reading', 'Science']   # simplify variable names 

pisa['Math'].plot(kind='barh')
```

**World Bank data.** 





## Resources 

Matplotlib 

* Matplotlib's [gallery of examples](http://matplotlib.org/gallery.html) is also a great starting point.  Find an example you like, download the code, and adapt it to your needs.   

<!-- 
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

Heatmaps:  http://stackoverflow.com/questions/14391959/heatmap-in-matplotlib-with-pcolor 

https://conference.scipy.org/scipy2013/tutorial_detail.php?id=103

Jake:  https://vimeo.com/53057312
http://jakevdp.github.io/mpl_tutorial/ 

Tufte interview:  http://adage.com/article/adagestat/edward-tufte-adagestat-q-a/230884/
-->
