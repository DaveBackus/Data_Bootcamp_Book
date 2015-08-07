# Where are we headed?

---

**Overview.**  Data skills are enormously valuable in the modern world.  We're going to give you those skills, show you how to apply them to economic and financial data, and maybe tell a few bad jokes along the way.  Join us!   

**Buzzwords.** Python, Google fu, code.  

---

This book -- and the course we developed it for -- is about data, primarily economic and financial data, which is what we know best. It's also about tools for working with data, which in this case means Python and its data-related packages.  If you make it to the end, you'll have a better idea where to find data that's useful to you.  You will also have command over tools you can use to do something interesting with it.  We think your life will be more interesting, but maybe that's us.  

## Answers to common questions 

**Why should I do this?**  It’s an investment in your future.  You will learn how to  process data and communicate its content effectively and efficiently.  You will be more valuable to current and future employers.   

**Can’t I do what I need in Excel?**  Excel is a great program, but once you have a little programming experience it will remind you of doing arithmetic on your fingers.  With Python, you will be able do routine tasks more efficiently (“[automate the boring stuff](https://automatetheboringstuff.com/),” as one guide suggests), handle larger data sets, and generally do things that spreadsheet programs can’t do.    

**What are the prerequisites?**  There are none.  We start at the very beginning and go from there.  What you'll need is the **courage** to take on a challenge and the **patience** to debug [programs that don’t quite work](http://junkcharts.typepad.com/numbersruleyourworld/2015/06/the-day-after-the-half-day-in-the-life-of-a-data-scientist.html) -- and they never work the first time, and often not the second or third time either.  Don't panic.  Ask for help and remind yourself that patience is a virtue. 

**What if my quant skills are weak or nonexistent?**  Then this is the course for you!  We do our best to make the material accessible.  We’re looking beyond quants to marketing, management, and humanities majors.  One of our design team was an English major.  

**Will this turn me into a programmer?**  You will come out of the course somewhere between Brad Pitt and Jonah Hill in “[Moneyball](http://www.imdb.com/title/tt1210166/)," with a solid foundation for dealing with whatever data comes your way.  You will not be ready for a career as a programmer, but you will be able to do things with data that Excel users can only dream about.  You will also be prepared to do more along similar lines, including the extensive collection of courses on **business analytics** and **data science** offered by NYU Stern's [IOMS group](http://www.stern.nyu.edu/experience-stern/about/departments-centers-initiatives/academic-departments/ioms-dept).  

**Should I take this course if I already know how to code?**  You’re welcome to, and you will learn a lot about data.  But please don’t scare the other students.  

**Is there anything Python can't do?**  Well, [it can't swallow a porcupine](http://www.telegraph.co.uk/news/worldnews/11697672/Python-chokes-to-death-after-eating-porcupine.html).  Someone is working on pretty much everything else.  

 
## Why data?  

We're living in a world of data: data about the economy, data about financial markets, data about your business.  Data doesn't solve all of our problems, but it's a valuable input to better decisions.  For example, how should you [choose a major](http://fivethirtyeight.com/features/the-economic-guide-to-picking-a-college-major/)?  

Many of our former students tell us that data skills keep them in business.  One of our alums analyzes television data for a network.  The datasets are too large for Excel, so he uses Python.  Another manages player and attendence data for a major league baseball team.  A third works for a quantitative hedge fund, where Python is the tool of choice.  A fourth is worried that you won't need him after this course. Even students with non-technical backgrounds tell us that basic data and programming skills are, if not absolutely required, at least very useful in their jobs.  One of marketing majors, for example, needs to interface with her company's SQL database to get the data she needs to do her job.  


## Why Python?   

[Python][10] is a popular general-purpose programming language that has been used for a broad range of applications. Google uses it.  So do Instagram and Netflix. Dropbox is written in Python.  

[10]: https://en.wikipedia.org/wiki/Python_(programming_language)

We think Python is the language of choice right now if you want a user-friendly introduction to programming and a useful tool for day-to-day data work.  It's a high-level language, which means the language does a lot of the work.  It has a  broad range of applications and an enormous community of users.  You'll come to appreciate both. And it's free and open source. Free means you pay nothing.  Open source means  you can look at the code if you want to see how something works.  

The closest competitors to Python for our purposes are probably [Matlab][1] and [R][2].  Matlab is a vector language, which means the kinds of things you do cell by cell in Excel you can do for a whole column or table in one line of code.  It was great in the 1980s, and we still use it for some things, but it's missing many of the convenient features of more modern languages.  It's not easy, for example, to read data straight from the internet. And functions must be stand-alone files, which gets annoying.  It's also expensive.  Outside universities, they seem to price it with investment banks in mind.  

[1]: https://en.wikipedia.org/wiki/MATLAB
[2]: https://en.wikipedia.org/?title=R_(programming_language)

R would be our second choice for data work after Python.  Like Python, it's free. It's the leading program among professional statisticians and has lots of  packages (add-ons) for data analysis. It's a great program, and it does lots of things, but it's not a general-purpose programming language. If you want to try it out, let us know, we can point you to some resources. The wildly popular [Introduction to Statistical Learning](http://www-bcf.usc.edu/~gareth/ISL/), for example, combines R with an introduction to modern statistical methods. 

Python is our first choice.  Although it's a general purpose language, we'll use it for data work, where it has become an able competitor to R. Our focus is economic and financial data, but the same methods can be applied to data from any source, including proprietary business data.  One of our former students is using it to study patterns of survival on the [Titanic](http://www.kaggle.com/c/titanic-gettingStarted) and Neilsen television ratings. Another is using it to [process text](http://www.nltk.org/) from news sources and analyst reports.  Thanks to hedge fund [AQR and others](http://pandas.pydata.org/community.html#history-of-development), the data-analytic toolsets in Python now rival stat-focused languages like R.   

That's our opinion anyway, but the larger point is that learning a programming language -- any language -- is better than not learning one.  We'll use Python, but you could do similar things in R -- and many do.  See also [this discussion](http://quant-econ.net/about_lectures.html#how-about-other-languages) from our friends Tom Sargent and John Stachurski.  Or [this one](http://www.dataschool.io/python-or-r-for-data-science/) from Kevin Markham. Or this [exchange](http://www.quora.com/Which-is-better-for-data-analysis-R-or-Python) on Quora.


## Everyone likes Python 

Python isn't just a useful language, it's one people like.  We're talking about programmers here, for the most part, but even us novices find that its casual simplicity makes coding fun. See, for example, this classic [xkcd cartoon](https://xkcd.com/353/). 

Paul Ford [puts it this way](http://www.bloomberg.com/graphics/2015-paul-ford-what-is-code/):  

> People love it and want it to work everywhere and do everything. They’ve spent tens of thousands of hours making that possible and then given the fruit of their labor away. That’s a powerful indicator. A huge amount of effort has gone into making Python practical as well as pleasurable to use. 

He's alluding here to the vast community of users who are developing tools that allows Python to do all kinds of things.  Python's data tools are an example:  they're not part of the core langauage, they're add-ons developed by users.  He adds:  "Python people are pretty cool," so there's that, too. (Ford's article, "What is Code," takes up a whole issue of Bloomberg BusinessWeek.  It's a classic, well worth the time.)  


## Wordplay

Python is named for Monty Python, a group of comedians whose humor appeals to the tech crowd.  Idle, a well-know Python editor, is a reference to Python-member Eric Idle.  The [Python Package Index](https://pypi.python.org/pypi), a repository of Python packages, is commonly known as the [Cheese Shop](http://youtu.be/PPN3KTtrnZM), a reference to a famous Monty Python skit.  The Anaconda distribution (next chapter) is a play on the word python.  



## Work habits

There are no shortcuts in learning how to code.  You simply need to spend hours -- and hours -- doing it.  Progress will seem slow at first, but if you stick with it things will start to look familiar, and even make sense. You may even think of projects and assignments as fun, and revel in your new-found power over data.  

As you work your way up the learning curve, keep this advice in mind:  

**Practice, practice, practice.**  Any time you have something to do with data, try it out in Python. Play around, try new things, have fun.  As you gain experience, you'll find that Python becomes your tool of choice.  

**Make friends.**  Coding is hard to do on your own.  A second pair of eyes is indespensible.  So work with friends, and make new friends who know how to code.  Intense coding sessions are a great way to develop relationships.  

**Work on your Google fu.**  You will find that many of your questions have been asked before -- and answered.  One way to find them:  Google something like "python [problem]."  There are answers in lots of places, but one of the best is [Stack Overflow](http://stackoverflow.com/questions/tagged/python).  

**Ask for help.**  If you get stuck, ask for help -- from friends, from your Bootcamp classmates (post a problem), or from us (the teachers of the course).  


## Our plan 

**Leap in.** We start quickly, which will seem like being dumped in a foreign country where you don't understand the language.  We do that so we can get to the things that interest us:  applications to data analysis.  That means that the work load is heaviest at the start.  Don't panic, the pace will slow down after the first 4-6 chapters -- and you'll learn a lot in the meantime.  

**Stress the basics.**  We think once you understand the basics, you'll be in a good position to work out special cases on your own.  Plus that allows us to strip out a bunch of confusing detail, which we think is good for everyone.  

**Code and applications.**  We attack data applications and programming together.  After covering Python basics, we generally organize things around specific applications, covering the relevant aspects of Python along the way.  We think it helps to have a context for what we're learning, but the downside is that it's somewhat harder to use the book as a programming reference.  We still think it makes sense.  Our goal isn't to produce programmers, but people who know enough about programming to work well with data.  

**Online book preferred.**  We sometimes print out the pdf ourselves, but the online version comes with links, color coding, and a more attractive layout.  We think it's a superior user experience -- but please tell us if you think we're wrong. 


## Resources 

All of the materials for this book and the associated course are posted on the web.  This book is hosted by [GitBook](https://www.gitbook.com/book/davebackus/test/details).  Other materials are available from our [GitHub repository](https://github.com/DaveBackus/Data_Bootcamp).  We give links to the relevant code at the start of each chapter, but if you want them all, look in the [Code directory](https://github.com/DaveBackus/Data_Bootcamp/tree/master/Code) of the GitHub repo.  


<!-- ## References ?? --> 

