# The data mentality

---
**Overview.** Thinking about data, ideas for projects.  Things to remember:  (i) Ideas aren't discovered, they're developed.  (ii) Ideas have friends:  when you find one, there are others nearby. 

**Buzzwords.** Questions, data, idea machines. 

**Trigger warning.**  There are way too many links here, be selective. 

**Code.** Related [examples](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/IPython/bootcamp_examples.ipynb).

---

Data analysis starts with a question.  Generally, we want to learn something.  In our world, we might ask:

*  **[What does the Chinese stock market boom and bust mean for the economy?](http://www.moneyandbanking.com/commentary/2015/7/6/chinas-stock-market-boom-and-bust).**
*  **[Why do tech companies come and go so quickly?](http://www.economist.com/techfirms).**
* **[What happens to GDP over time and across nations?](http://www.gapminder.org/world/).**
* **[What share of income goes to the one percent?](http://ramiro.org/notebook/top-incomes-share/).** 
* Sometimes we even let our minds wander from finance and economics long enough to pondering life and the universe and ask: **[How and when are we most likely to die?](http://www.bloomberg.com/dataview/2014-04-17/how-americans-die.html)** and **[What's going on in New York City?](http://iquantny.tumblr.com/)**

The starting point is a question, something you'd like to know more about.  You provide the question. We provide a toolkit for effectively working with data to find answers.  Many of our examples are about economics and finance, because that's what we know.  But the same tools can be used to address any data questions we like.    

Once we have a question, we can start looking for data that might help us come up with an answer. This leads to more questions:  
* What data would be helpful in answering our question?  
* Where can we find it?  
* What should we do with it once we have it?  


## Thinking about data 

It's not that we have no lives or anything, but we think about data all the time.  If we see an interesting graphic in *The Economist* -- or the *Wall Street Journal*, or the *New York Times* -- it triggers a series of questions.  Where does the data come from?  Can we get it ourselves?  (We can help with this one.) Can we reproduce the graphic?  Can we improve it?  What else would we like to know?  

This isn't something you need to do on your own --  it's way more fun to **talk to others**, especially if you can get free work out of them.  Look at the examples above, ask your friends what they think.  Post a question or comment on our Google Group.  

**Exercise.** The 538 blog has a nice summary of [salaries of recent college graduates](http://fivethirtyeight.com/features/the-economic-guide-to-picking-a-college-major/).  Skip to the bottom to sort by major and play around. Answer these questions:
* What did you learn from their table?  
* What else would you like to know?  
* Where did they get their data?  

**Exercise.** What kinds of things would you like to know more about?  Think of this as improv, there are no bad answers. 


## Generating project ideas 

One of our goals is for you to produce a piece of work -- data and graphics -- that you can show potential employers.  There's nothing like a concrete example (regardless of the topic) to show off your skill set.  It's early in the semester, but it can't hurt to start thinking about this.

**Sample projects.** A typical project might be a short report that uses data and graphics to make a point. Here are some examples of what your final output might resemble:  
 
* **[US employment](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/Projects/Employment-Population-Ratio_DavidCai_Jul_15.ipynb).**  Student David Cai documents the recent decline in the fraction of adults working in the US.  But why?
* **[Reinhardt-Rogoff revisited](http://nbviewer.ipython.org/github/vincentarelbundock/Reinhart-Rogoff/blob/master/reinhart-rogoff.ipynb).**  Vincent Arel-Bundock reproduces the [famous mistake](http://www.bloomberg.com/bw/articles/2013-04-18/faq-reinhart-rogoff-and-the-excel-error-that-changed-history) in which Reinhard-Rogoff's Excel errors changed their analysis of government debt's relationship with slow economic growth (yes, they should be embarrassed for using Excel).
* **[Gender ratios by county](http://thomaz.me/data/visualizing-census-data-with-google-fusion-tables-tutorial/).**  
* **[Box office booms and busts](http://www.randalolson.com/2014/12/29/the-biggest-box-office-booms-and-busts-since-1982/).**  
* **[Textbooks prices by major](http://priceonomics.com/which-major-has-the-most-expensive-textbooks/).**
* **[NBA shot charts](http://savvastjortjoglou.com/nba-shot-sharts.html).**  Even if you're not a basketball fan, this is a terrific project that produces some great pictures and shows you how along the way.  Here's the [IPython notebook](https://github.com/savvastj/blog/blob/master/content/NBA_shot_charts.ipynb) - you'll learn more about IPython notebooks later.   
* **[Twitter profiles](http://andrewshamlet.com/2015/07/13/part-3-most-common-words-used-in-tweets-by-taylor-swift-katy-perry-and-britney-spears/).**  Student Andrew Hamlet mines twitter data and documents patterns in tweets by Taylor Swift and others. 


Here are some good starting points:  

* Start with what interests you:  Economics, finance, marketing, emerging markets, movies, sports. 
* Start with the output you'd like:  Find an analyst report, blog post, or graphic you like, ask where the data comes from, think about whether you can replicate and/or extend it.   
* Start with an input:  Find a dataset you find interesting, ask what you might do with it.  

**Idea machines.**  Another way to generate ideas is to skim articles or blog posts that use data and graphics.  A graphic that makes a compelling point is a wonderful thing.  Take some time, find a comfortable chair, and look through a few of our favorite examples.  

* **Blogs with data.**  [Conversable Economist](http://conversableeconomist.blogspot.com/), [FRED blog](https://fredblog.stlouisfed.org/), [R-bloggers](http://www.r-bloggers.com/), Prof. Vishal Singh's [website](http://www.d3mprof.com/) for his course, Data-Driven Decision Making.

* **Data journalism.** [538](http://fivethirtyeight.com/), [Upshot](http://www.nytimes.com/upshot/), [Quartz](http://qz.com/).  Some of them post data and code as well (look for their GitHub repositories).  See, for example, 538's [analysis of Uber and taxi data](http://fivethirtyeight.com/features/public-transit-should-be-ubers-new-best-friend/).  
* **Graphics blogs.**  [Flowing data](https://flowingdata.com/), [Junk Charts](http://junkcharts.typepad.com/), [VizWiz](http://vizwiz.blogspot.com/), [Data Viz Done Right](http://www.datavizdoneright.com/), [Graphic detail](http://www.economist.com/blogs/graphicdetail).  And here are a [couple](http://flowingdata.com/2012/04/27/data-and-visualization-blogs-worth-following/) [lists](http://vizwiz.blogspot.com/p/data-viz-blogs.html). The [Tableau public gallery](http://public.tableau.com/s/gallery) also has some good examples, including [this one](https://public.tableau.com/s/gallery/dementia-uk). ([Tableau](http://www.tableau.com/) is a popular "data visualization" program.) 

* **Datasets.**  [FRED](https://research.stlouisfed.org/fred2/series/GDP) is our go-to source for macroeconomic data.  The "Notes" tab gives us the original source if we want to dig deeper.  The [World Bank](http://data.worldbank.org/) has a huge collection of emerging market indicators.  And here are [three](http://www.asdfree.com/p/about-faq.html) [good](https://sites.google.com/site/medevecon/development-economics/devecondata) [lists](http://flowingdata.com/2009/10/01/30-resources-to-find-the-data-you-need/) of data sources. You can also use your Google fu.  

* **Even more resources** We've put together a longer [list of project ideas](https://docs.google.com/document/d/1hsuYz2IMoPPwba66BlyMW0tnMxuZPyH4F3ybc13Zsfk/edit?usp=sharing), or if you're feeling brave, you could also take a look at our [enormous collection](https://docs.google.com/document/d/1L2ZDKFyyqfOrCGbNcCIE9mmgap4tjkTNuw32hK4c6BI/edit?usp=sharing) of economic, financial, and miscellaneous data sources and applications.

* **Helpful video:** If you have an hour, watch Steve Levitt's [video](https://youtu.be/r5jATFtKtI8?t=5m10s) about working with company data. Entertaining and informative. 


**Common mistakes -- and how to fix them.**  We mean this in a good way, but in our experience there are a number of things students do that make this harder than it should be.  Here's a list, with suggestions for overcoming them: 

*  **Mistake: Reject an idea too soon,** before you’ve given it enough thought.  Solution:  Don't be critical too early.  Collect ideas first, whittle them down later.    
*  **Mistake: Choose a project that’s too large**.  Solution:  Keep it simple.  Think it over for a while, and choose a small part of a larger project that is interesting on its own.  You can always do more later.   
*  **Mistake:  Your dataset doesn't have everything you want.**  To be honest, that's pretty much every dataset we've ever seen.  Solution:  Make do with what you have.  
*  **Mistake:  Pick a dataset that's not available.**  Solution:  Start with what you have, ask what you can do with it.  We call this the [Jeopardy](https://en.wikipedia.org/wiki/Jeopardy!) approach:  start with the answer, come up with the question.  If that fails, find another dataset.  

**Bottom line.**  Projects are less structured than most things you'll run across in the academic world.  It's challenging, at first, to work with so little structure, but most students find that the freedom to develop their own projects is one of the most rewarding things they can do.  

**Exercise.**  Write down four project ideas.  Don't overthink this, one or two lines each will do.  