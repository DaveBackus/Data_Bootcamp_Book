# The data mentality

---
**Overview.** Thinking about data, ideas for projects.  Things to remember:  (i) Ideas aren't discovered, they're developed.  (ii) Ideas have friends:  when you find one, there are others nearby. 

**Buzzwords.** Questions, data, idea machines. 

**Trigger warning.**  There are way too many links here, be selective. 

**Code.** Related [examples](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/IPython/bootcamp_examples.ipynb).

---

**UNDER CONSTRUCTION** 

Data analysis starts with a question.  Generally, we want to learn something.  In our world, we might ask

* How is the US economy doing?  
* How does average income vary across countries?  Across states?  Across zip codes?  
* What emerging market countries offer the best business opportunities? 
* How do returns on US and European stocks compare?   
* What college majors lead to the highest salaries?  

You get the idea.  The starting point is a question, something we'd like to know more about.  The question comes from you.  What we provide is a mentality for thinking about data and a toolkit for working with it ffectively.  We focus on questions about economics and finance, because that's what we know.  But the same tools can be used to address any data questions we like.    

Once we have a question, we can start looking for data that might help us come up with an answer, or at least inform an answer. Which leads to more questions:  What data would be helpful in answering our question?  Where can we find it?  What should we do with it once we have it?  



## Thinking about data 

It's not that we have no lives or anything, but we think about data all the time.  If we see an interesting graphic in *The Economist* -- or the *Wall Street Journal*, or the *New York Times*, or a blog post -- it triggers a series of questions.  Where does the data come from?  Can we get it ourselves?  (We can help with this one.) Can we reproduce the graphic?  Can we improve it?  What else would we like to know?  

You can ask the same questions yourself.  Here are some examples to practice on (click on the ones that inteerst you):  

<!-- * **[FRED](https://research.stlouisfed.org/fred2/series/GDP).**  Our go-to source for macroeconomic data.  The "Notes" tab gives us the original source if we want to dig deeper.  
* **[Gapminder world](http://www.gapminder.org/world/).**  Great interactive graphic.  The [data page](http://www.gapminder.org/data/) gives sources. -->


Somewhere?  http://iquantny.tumblr.com/ ??

* **[Chinese stock prices](http://www.moneyandbanking.com/commentary/2015/7/6/chinas-stock-market-boom-and-bust).**  Steve Cecchetti and Kim Schoenholtz comment on the boom and bust and what it means for the development of China's financial institutions.   
* **[Market caps of tech firms](http://www.economist.com/techfirms).**  Note how quickly tech firms come and go.  Is that true of other industries? 
* **[Gapminder world](http://www.gapminder.org/world/).**  Great interactive graphic.  Give it a few seconds to load, then press the play button in the lower left corner.  What do you see?  What other data is available?  The [data page](http://www.gapminder.org/data/) gives sources if you want to follow up.   
* **[Economic mobility](http://www.nytimes.com/2013/07/22/business/in-climbing-income-ladder-location-matters.html).**  We love maps.  This one shows that kids do better (relative to their parents) in some places than others.  Why is that?  What's wrong with the South?  Why don't kids do better in New York? 
* **[Oil supply and demand](http://econbrowser.com/archives/2015/10/supply-demand-and-the-price-of-oil-2).**  World oil prices [dropped like a stone](https://research.stlouisfed.org/fred2/series/DCOILBRENTEU) in 2014. Why? Jim Hamilton explains what we know.    
* **[The one percent](http://ramiro.org/notebook/top-incomes-share/).**  What share of income went to the top one percent?  Data for lots of countries over almost a century.  
* **[V-Lab](http://vlab.stern.nyu.edu/en/).**  Rob Engle's market volatility website.  Data and graphs of volatility for US and Chinese stocks, currencies, government bonds, and many other things.  
* **[Kaiser Slides](http://kff.org/kaiser-slides/).**  Healthcare-related charts from the Kaiser Family Foundation.   
* **[Vaccination heatmaps](http://graphics.wsj.com/infectious-diseases-and-vaccines/).**  A striking visual representation of diseases over time, motivated by the decisions of some [rich people in California](http://www.nytimes.com/interactive/2015/02/06/us/california-measles-vaccines-map.html) [not to vaccinate](http://www.washingtonpost.com/blogs/wonkblog/wp/2015/01/27/californias-epidemic-of-vaccine-denial-mapped/) their children.  Here's a related [blog post](https://benjaminlmoore.wordpress.com/2015/04/09/recreating-the-vaccination-heatmaps-in-r/) with R code.  (Which reminds us:  If you see R code, you should think, great, we can convert it to Python.)
* **[Bloomberg on mortality](http://www.bloomberg.com/dataview/2014-04-17/how-americans-die.html).**  This is really cool.  It's beyond us technically, at least for the moment, but the ingredients are all things we can access.  And between us friends, the decline in mortality (people are living longer) is one of the most interesting facts about the modern world.  Check Gapminder on life expectancy if that doesn't strike you.  

Which ones do you like?  What did you like about them?  What would it take for you to reproduce them?  Do they suggest followup questions?  

This isn't something you need to do on your own --  it's way more fun to **talk to others**, especially if you can get free work out of them.  Ask your friends what they think.  Post a question or comment on our Google Group.  

<!-- Or (this is less social, but useful) Google the topic and see what else pops up. -->


**Exercise.** The 538 blog has a nice summary of [salaries of recent college graduates](http://fivethirtyeight.com/features/the-economic-guide-to-picking-a-college-major/) sorted by major (skip to the bottom for the sortable table).  What did you learn from their table?  What else would you like to know?  Where did they get their data?  

**Exercise.** What kinds of things would you like to know more about?  Think of this as improv, there are no bad answers.  


## Generating project ideas 

One of our goals is for you to produce a piece of work -- data and graphics -- that you can show potential employers.  There's nothing like a concrete example to show off your skill set.  Don't worry about the topic, it's the skill set you're showing off.  We're getting a little ahead of ourselves, but we thought it would be useful to talk about finding project ideas now so we all know where we're headed.  


**Sample projects.** A typical project might be a short report that uses data and graphics to make a point. Here are some examples, chosen more for style than content, but feel free to add your own ideas:    

<!-- **Refine this, more emphasis on econ/fin projects** -->

* **[Trend growth in the US](http://www.moneyandbanking.com/commentary/2015/2/23/forecasting-trend-growth-living-with-uncertainty).**  Steve Cecchetti and Kim Schoenholtz document the drop in our estimates of trend growth?  What happened?  Why?   
* **[US employment](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/Projects/Employment-Population-Ratio_DavidCai_Jul_15.ipynb).**  Student David Cai documents the recent decline in the fraction of adults working in the US.  The question is why. Are we getting lazier?  Or something else? 
* **[Africa in numbers](http://www.theguardian.com/commentisfree/datablog/2015/sep/10/africa-in-numbers-how-its-countries-compare).**  Nice overview of African countries from the Guardian's data group.  
* **[Reinhardt-Rogoff revisited](http://nbviewer.ipython.org/github/vincentarelbundock/Reinhart-Rogoff/blob/master/reinhart-rogoff.ipynb).**  Vincent Arel-Bundock reproduces the [famous mistake](http://www.bloomberg.com/bw/articles/2013-04-18/faq-reinhart-rogoff-and-the-excel-error-that-changed-history).  Carmen Reinhardt and Ken Rogoff claimed high levels of government debt were associated with slower economic growth.  The association is there, but it's slight once you eliminate their Excel errors.  (Yes, they should be embarrassed for using Excel. But no, it's still not a good idea to run up loads of debt.)  
* **[Gender ratios by county](http://thomaz.me/data/visualizing-census-data-with-google-fusion-tables-tutorial/).**  Another map.  The same approach can be used to deal with lots of other census data:  income, age, education, ethnicity, and many other things.  
* **[Movie hits](http://www.randalolson.com/2014/12/29/the-biggest-box-office-booms-and-busts-since-1982/).**  Movie data is always interesting, we'll see more of it later on. 
* **[Textbooks](http://priceonomics.com/which-major-has-the-most-expensive-textbooks/).** Why are they so expensive?  What majors have the most expensive books?  (Not us, you may notice.) 
* **[NBA shot charts](http://savvastjortjoglou.com/nba-shot-sharts.html).**  Even if you're not a basketball fan, this is a terrific project that produces some great pictures and shows you how along the way.  Here's the [IPython notebook](https://github.com/savvastj/blog/blob/master/content/NBA_shot_charts.ipynb). 
* **[Student debt](http://www.nytimes.com/2015/09/01/upshot/why-students-with-smallest-debts-need-the-greatest-help.html).**  The best part is the [link](http://ifap.ed.gov/eannouncements/082015FederalStudentAidPostsUpdatedReportstoFSADataCenter.html) to the data.  
* **[Uber and taxis](http://fivethirtyeight.com/features/uber-is-serving-new-yorks-outer-boroughs-more-than-taxis-are/).**  Evidently they're doing a better job than taxis of serving the outer boroughs of NYC. Data [here](https://github.com/fivethirtyeight/uber-tlc-foil-response).  
* **[Twitter profiles](http://andrewshamlet.com/2015/07/13/part-3-most-common-words-used-in-tweets-by-taylor-swift-katy-perry-and-britney-spears/).**  Student Andrew Hamlet mines twitter data and documents patterns in tweets by Taylor Swift and others. 
* **[Citibikes](https://wakari.io/sharing/bundle/paddy/pydata_citibike).**  This service comes with a public data interface, one of many provided by local governments. Here's [another one](https://jakevdp.github.io/blog/2015/07/23/learning-seattles-work-habits-from-bicycle-counts/) about bikes, this time for Seattle.  There's a link to the IPython notebook at the end.  

You may have noticed that several of these are **IPython notebooks**.  We'll learn more about them shortly.  Their value in this context is that they combine code with text and graphics.  They allow us to show off not only what we've done but how we've done it.  


**Starting points.**  If you're looking for ideas, you can start almost anywhere.  We like to say that **ideas are developed, not discovered**.  Good ideas generally don't jump immediately to mind, they take some time to evolve.  Be open to ill-formed thoughts, they sometimes turn into great ones.   We also like to sat that **ideas have friends**:  once you have one, others often pop up.  The key is to get started:  take one step, and see where it leads.  

Here are some good starting points:  

* Start with what interests you:  Economics, finance, marketing, emerging markets, movies, sports. 
* Start with the output you'd like:  Find an analyst report, blog post, or graphic you like, ask where the data comes from, think about whether you can replicate and/or extend it.   
* Start with an input:  Find a dataset you find interesting, ask what you might do with it.  

The suggestion is to start somewhere -- anywhere -- and see where it leads.  Bounce around ideas with friends.  Go for a long walk.  Keep your mind open.  


**Idea machines.**  Another way to generate ideas is to skim articles or blog posts that use data and graphics.  A good graphic is a wonderful thing, especially one that makes a compelling point.  Here are some of our favs.  Take an hour some time, find a comfortable chair, and look through some of them.  

* **Blogs with data.**  [Conversable Economist](http://conversableeconomist.blogspot.com/), [FRED blog](https://fredblog.stlouisfed.org/), [R-bloggers](http://www.r-bloggers.com/). There are lots more, but that's a start.      
* **Data journalism.** [538](http://fivethirtyeight.com/), [Upshot](http://www.nytimes.com/upshot/), [Quartz](http://qz.com/).  Some of them post data and code as well (look for their GitHub repositories).  See, for example, 538's [analysis of Uber and taxi data](http://fivethirtyeight.com/features/public-transit-should-be-ubers-new-best-friend/).  
* **Graphics blogs.**  [Flowing data](https://flowingdata.com/), [Junk Charts](http://junkcharts.typepad.com/), [VizWiz](http://vizwiz.blogspot.com/), [Data Viz Done Right](http://www.datavizdoneright.com/), [Graphic detail](http://www.economist.com/blogs/graphicdetail).  And here are a [couple](http://flowingdata.com/2012/04/27/data-and-visualization-blogs-worth-following/) [lists](http://vizwiz.blogspot.com/p/data-viz-blogs.html). The [Tableau public gallery](http://public.tableau.com/s/gallery) also has some good examples, including [this one](https://public.tableau.com/s/gallery/dementia-uk). ([Tableau](http://www.tableau.com/) is a popular "data visualization" program.) 

http://dadaviz.com/

* **Datasets.**  [FRED](https://research.stlouisfed.org/fred2/series/GDP) is our go-to source for macroeconomic data.  The "Notes" tab gives us the original source if we want to dig deeper.  The [World Bank](http://data.worldbank.org/) has a huge collection of emerging market indicators.  And here are [three](http://www.asdfree.com/p/about-faq.html) [good](https://sites.google.com/site/medevecon/development-economics/devecondata) [lists](http://flowingdata.com/2009/10/01/30-resources-to-find-the-data-you-need/) of data sources. You can also use your Google fu.  


**Common mistakes -- and how to fix them.**  We mean this in a good way, but in our experience there are a number of things students do that make this harder than it should be.  Here's a list, with suggestions for overcoming them: 

* Mistake:  **Reject an idea too soon,** before you’ve given it enough thought.  Solution:  Don't be critical too early.  Collect ideas first, whittle them down later.    
* Mistake:  **Choose a project that’s too large**.  Solution:  Keep it simple.  Think it over for a while, and choose a small part of a larger project that is interesting on its own.  You can always do more later.   
* Mistake:  **Your dataset doesn't have everything you want.**  To be honest, that's pretty much every dataset we've ever seen.  Solution:  Make do with what you have.  
* Mistake:  **Pick a dataset that's not available.**  Solution:  Start with what you have, ask what you can do with it.  We call this the [Jeopardy](https://en.wikipedia.org/wiki/Jeopardy!) approach:  start with the answer, come up with the question.  If that fails, find another dataset.  

**Bottom line.**  Projects are less structured than most things you'll run across in the academic world.  It's challenging, at first, to work with so little structure, but most students find that the freedom to develop their own projects is one of the most rewarding things they can do.  

**Exercise.**  Write down four project ideas.  Don't overthink this, one or two lines each will do.  

We've given you way too much information.  We suggest you spend a couple hours some time in a comfortable spot, skim through the links, and write down anything that interests you.  Stop when your find your eyes blurring.  


## Resources 

We've put together a longer [list of project ideas](https://docs.google.com/document/d/1hsuYz2IMoPPwba66BlyMW0tnMxuZPyH4F3ybc13Zsfk/edit?usp=sharing), some more fleshed out than others.  Give them a skim, see what appeals to you.  Or come up with your own.  

If you're feeling brave, you could also take a look at our [enormous collection](https://docs.google.com/document/d/1L2ZDKFyyqfOrCGbNcCIE9mmgap4tjkTNuw32hK4c6BI/edit?usp=sharing) of economic, financial, and miscellaneous data sources and applications.  It's what our Aussie friend John Asker would call a dog's breakfast, but we're convinced there's lots of cool stuff hidden there. Or you could look at some of the examples on the [website](http://www.d3mprof.com/) fr Vishal Singh's course, Data-Driven Decision Making.  Actually, you might want to go there first, it has some great stuff.  

Finally, if you have an hour to spend (productively), watch Steve Levitt's [video](https://youtu.be/r5jATFtKtI8?t=5m10s) comments about working with company data.  Entertaining and informative. 

<!-- ??
**For later:  divide these links into econ/fin and other.  Do this throughout the chapter.**
-->