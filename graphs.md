# Visualizing data 


---
**Overview.**  We introduce and apply Python's popular graphics package, Matplotlib.  

**Python tools.**  Graphing with Matplotlib.

**Buzzwords.** Packages (libraries, modules), data visualization.  

**Applications.**  Incomes of college majors.??

---

Computer graphics are one of the great advances of the modern world.  Graphs have always been helpful in describing data or concepts, but they're a lot easier to produce now than they were a few years ago. In fact, we've gotten so good at drawing pictures that we invented a new term for it:  **visualization**.  

That's the good news.  The bad news, or at least the reigning fact of life, is that graphics are inherently complicated.  Programs like Excel do their best to hide this fact, but if you ever try to customize a chart it quickly rears its ugly head.  A graph's features might include, for example:  the type (line, bar, etc); the color and thickness of lines, bars, or markers; title and axis labels; their location, fonts, and font sizes; tick marks (location, size); background color; grid lines (on or off); and so on.  So there's lots of stuff to keep track of.  

We introduce graphics with **Matplotlib**, the leading collection of graphics tools in Python.  



## Reminders 


lists 


functions and methods... 


## IPython notebooks 

basics...

markdown...  

matplotlib flag 


##  Matplotlib 1:  the pyplot module 

Functions and methods...



## Object-oriented matplotlib




## Style sheets 

```
import matplotlib.pyplot as plt

# http://matplotlib.org/users/style_sheets.html
plt.style.use('ggplot')
plt.style.reload_library()  # does this reset default?  
```


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


## Examples 

http://fivethirtyeight.com/datalab/the-extreme-economic-outlier-that-is-greece-in-7-charts/



## Resources 

* Matplotlib's [Pyplot tutorial](http://matplotlib.org/users/pyplot_tutorial.html) is excellent. 

* Matplotlib's [gallery of examples](http://matplotlib.org/gallery.html) is also a great starting point.  Find an example you like, download the code, and adapt it to your needs.   

* Rougier, Mueller, and Varoquaux's [SciPy lecture notes](https://scipy-lectures.github.io/intro/matplotlib/matplotlib.html) are also quite good.  It's aimed at scientists, so the examples tend to be mathematical.  Their [cookbook](http://wiki.scipy.org/Cookbook/Matplotlib) has a good collection of samples.  

* Sargent and Stachurski's [Quantitative Economics](http://quant-econ.net/) has a good overview of Matplotlib, but we find it a little terse.  

* [Practical business Python](http://pbpython.com/visualization-tools-1.html) is a terrific blog.  This post concerns Python visualization packages.  He likes Seaborn.  




