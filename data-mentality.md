# The data mentality


---
**Overview.** Thinking about data, project ideas.  

---


Data analysis starts with a question.  Generally, we want to learn something.  In our world, we might ask

* What emerging market countries offer the best business environments?
* How is the US economy doing right now?  
* How do returns on US and European stocks compare?    
* How does average income vary across countries?  Across states?  Across zip codes?  
* What college majors lead to the best jobs?  

You get the idea.  The starting point is a question, something you'd like to know, not the data itself.  

Once we have a question, we can start looking for data that might help us come up with an answer. We might ask ourselves:  What data would be helpful in answering our question?  Where can we find it?  What should we do with it once we have it?  

The question comes from you.  What we provide is a mentality for thinking about data and a toolset to work with it effectively.  


## Start thinking about data 

It's not that we have no lives or anything, but we think about data all the time.  If we see an interesting graphic in *The Economist* -- or the *Wall Street Journal*, or the *New York Times*, or a blog post -- we look immediately for the source.  Is it one we know?  Can we get it ourselves?  If we have the data, do we have the tools to reproduce the graphic?  

You can ask the same questions yourself.  Here are some examples to practice on:  

* [FRED](https://research.stlouisfed.org/fred2/series/GDP).  Our go-to source for macroeconomic data.  The "Notes" tab gives us the original source if we want to dig deeper.  
* [Gapminder world](http://www.gapminder.org/world/).  Great interactive graphic.  The [data page](http://www.gapminder.org/data/) gives sources.  
* [Market caps of tech firms](http://www.economist.com/techfirms).  Interesting to see how quickly tech firms come and go.  Is that true of other industries? 
* [Economic mobility by region](http://www.nytimes.com/2013/07/22/business/in-climbing-income-ladder-location-matters.html).  We love maps.  This one shows that kids do better (relative to their parents) in some places than others.  Why is that?  What's wrong with the South?  
* [Vaccination heatmaps](http://graphics.wsj.com/infectious-diseases-and-vaccines/).  A striking representation of diseases over time, probably motivated by the decisions of some [rich people in California](http://www.nytimes.com/interactive/2015/02/06/us/california-measles-vaccines-map.html) [not to vaccinate](http://www.washingtonpost.com/blogs/wonkblog/wp/2015/01/27/californias-epidemic-of-vaccine-denial-mapped/) their children.  Here's a related [blog post](https://benjaminlmoore.wordpress.com/2015/04/09/recreating-the-vaccination-heatmaps-in-r/) with R code.  (Which reminds us:  If you see R code, you should think, great, we can convert this to Python.)
* [Bloomberg on mortality](http://www.bloomberg.com/dataview/2014-04-17/how-americans-die.html).  This is really cool.  It's beyond us technically, at least for the moment, but the ingredients are all things we can access.  And between us friends, the decline in mortality (people are living longer) is one of the most interesting things about the modern world.  Check Gapminder on life expectancy if that doesn't strike you.  

Which ones do you like?  What did you like about them?  What would it take for you to reproduce them?  Do they suggest followup questions?  

This isn't something you need to do on your own --  it's way more fun to talk to others, especially if you can get free work out of them.  Ask your friends what they think.  Post a question or comment on our Google Group.  Or (this is less social, but useful) Google the topic and see what else pops up. 


**Exercise.** The 538 blog has a nice summary of [salaries of recent college graduates](http://fivethirtyeight.com/features/the-economic-guide-to-picking-a-college-major/) sorted by major (skip to the bottom for the sortable table).  What did you learn from their table?  What else would you like to see?  Where did they get the data?  

**Exercise.** What kinds of things would you like to know more about?  Think of this as improv, there are no bad answers.  


## Projects 

One of our goals is for you to have a piece of work -- data and graphics -- that you can show potential employers.  There's nothing like a concrete example to show off your skill set.  Don't worry about the topic, it's the skill set you're showing off.  We're getting a little ahead of ourselves, but we thought it would be useful to talk about this now so we all know where we're headed.  


**Sample projects.** A typical project might be an IPython notebook that uses data to make a point. Here are some examples, chosen more for style than content, but feel free to suggest your own:  

* [NBA shot charts](http://savvastjortjoglou.com/nba-shot-sharts.html).  If you're into that kind of thing.  Honestly, this is a terrific project that produces some great pictures and shows you how along the way.  Here's the [IPython notebook](https://github.com/savvastj/blog/blob/master/content/NBA_shot_charts.ipynb).   
* [US employment](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/Projects/Employment-Population-Ratio_DavidCai_Jul_15.ipynb).  David Cai documents the recent decline in the fraction of adults working.  The question is why. Are we getting lazier?  Or something else?  
* [Movie hits and busts](http://www.randalolson.com/2014/12/29/the-biggest-box-office-booms-and-busts-since-1982/).  
* [Reinhardt-Rogoff replication](http://nbviewer.ipython.org/github/vincentarelbundock/Reinhart-Rogoff/blob/master/reinhart-rogoff.ipynb).  This reproduces the mistake in the famous paper that claimed high levels of government debt were associated with slower economic growth.  The association is slight.  
* [Citibike usage](https://wakari.io/sharing/bundle/paddy/pydata_citibike).  
* [More cycling](https://jakevdp.github.io/blog/2015/07/23/learning-seattles-work-habits-from-bicycle-counts/).  Interesting use of graphics to summarize data.  There's a link to the notebook at the end.  


**Starting points.**  If you're looking for ideas, you can start almost anywhere.  And we like to say **ideas have friends**:  once you have one idea, several others often pop into your mind. Here are some starting points:  

* Start with what interests you:  economics, finance, marketing, emerging markets, movies, sports 
* Start with output:  find an analyst report, blog post, or graphic you like, ask where the data comes from, whether you can replicate/extend 
* Start with input:  Economics and finance data:  huge universe of stuff, what can you do with it? 
Develop what you have:  all starting points lead to others, bounce around ideas over coffee with friends, take a long walk 

We've also put together a [list of project ideas](https://docs.google.com/document/d/1hsuYz2IMoPPwba66BlyMW0tnMxuZPyH4F3ybc13Zsfk/edit?usp=sharing), some more fleshed out than others.  Give it a skim, see what appeals to you.  


**Idea machines.**  Another way to generate ideas is to skim blogs that look at data and graphics.  The latter is a reminder of the form of our output.  A good graphic is a wonderful thing, especially one that makes a compelling point.  Here are some of our favs.  Take an hour or two some time, find a comfortable chair, and look throughh them.  

* Blogs that often have data and graphics:  [Conversable Economist](http://conversableeconomist.blogspot.com/), [FRED blog](https://fredblog.stlouisfed.org/), [R-bloggers](http://www.r-bloggers.com/), .  
* Data journalism:  [538](http://fivethirtyeight.com/), [Upshot](http://www.nytimes.com/upshot/), [Quartz](http://qz.com/.  They often post data and code as well (look for their GitHub repositories).  
* Graphics blogs:  [Flowing data](https://flowingdata.com/), [Junk Charts](http://junkcharts.typepad.com/), [VizWiz](http://vizwiz.blogspot.com/), and [Data Viz Done Right](http://www.datavizdoneright.com/).  And here are a [couple](http://flowingdata.com/2012/04/27/data-and-visualization-blogs-worth-following/) [lists](http://vizwiz.blogspot.com/p/data-viz-blogs.html). Also the [Tableau public gallery](http://public.tableau.com/s/gallery).  


**Common mistakes -- and solutions to them.**  The idea is to keep this positive, but in our experience there are a number of things students do that make this harder than it should be.  Here's a list, with suggestions for overcoming them: 

* Mistake:  **Reject an idea too soon,** before you’ve given it enough thought.  Solution:  Collect ideas first, whittle them down later.  
* Mistake:  Choose **a project that’s too large**.  Solution:  Think it over for a while, choose a small part that you think is interesting on its own.  You can always do more later.   
* Mistake:  Pick a **bad dataset**, one that’s not available or doesn’t have what you need.  Solution:  Start with what you have, ask what you can do with it.  We call this the Jeopardy approach:  start with the answer, come up with the question. 


Bottom line.  Projects are less structured than most things you'll run across in the academic world.  That's challenging at first, but most students find that the freedom to develop their own work is one of the most rewarding things they can do.  


## Resources 

??
??

Project ideas:  https://docs.google.com/document/d/1hsuYz2IMoPPwba66BlyMW0tnMxuZPyH4F3ybc13Zsfk/edit?usp=sharing 

