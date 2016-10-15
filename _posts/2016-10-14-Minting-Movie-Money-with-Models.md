---
layout: post
title:  Minting Movie Money with Modeling
date:   2016-10-1 13:03:45
categories: Metis Movies Projects
---
I had the opportunity to work on an **interesting** and **challanging** project over the past two weeks.  I think I can safely say iteration 1 is shipped at this point.

### The Question:

#### Given information that would be available to early stage investors, is it possible to accuarately predict the return on investment for a proposed film production?


One of the most important things you need when approaching a new data science question is **domain knowledge**.  Going into this I had some insight from previous careers, however I knew that wouldn't be enough.  I have a [good friend Anthony][ant], who works as a motion picture sound editor.  Through him, and one of his [excellent contacts Brian][brian], I was able to get some interesting baseline knowledge about how movies are made, and more importantly,  how they are financed.  We discussed many factors, but these stuck out as important to me:

+ **Profits generated** by a production, are generally split, with 50% going to the production company or studio, and the remainder going to investors, usually multiple are involved 


+ **Investment models** are often **equity** based, meaning investors take a smaller intrest position on the loan, and receive a share of the profit split.


+ **The most risk** is shouldered by early stage investors, they have the least amount of information upon which to make a decision and negotiate terms.


+ **Early stage investors** can reap the highest rewards.  They can receive between 25-50% of the profit split, and they are the first to be paid back when a project is released.


+ **Opening weekend** is becoming **less** important than it used to be, likely due in part to the expansion into new markets and platforms where one can sell their films.


Armed with my new found domain knowledge, I first did some brainstorming so as to formulate a plan of attack where feature engineering is concerned.  I asked myself a few questions:


+ **What makes a great movie?**  Incredibly broad, but upon thinking about it, I decided that great movies are inherently driven by the people who work on them, and how they synergize with one another.  It's in no way a given, [Gigli][G], but it's certainly worked out for Tarentino.


+ **What makes a profitable movie?**  This is a difficult question to answer, and really is the core of what I set out to do, however I hypothesized that genre, cast, crew budget, and timing would all play a role.  I'm sure the list goes on,  but I didn't want to overscope myself too early in the process, I still needed data.


## Acquire Data

Now that I had some good insider knowledge and what I beleived to be a strong angle of approach, it was time to find the data.  I zeroed in on three seprate sources for data collection:


+ **[The Movie DataBase][tmdb]**

+ **[The Movie Lens project][tml]**

+ **[Box Office Mojo][bom]**


I went through at leat 5, often painful, rounds of HTML scraping and API calls. I seriously considered quitting data science to be a full time evangalist for well maintained consistent API's.  What a diffrence they make.  Turns out not everyone wants to publicize their production budjet.  From a starting set of over 9,700 movies, I ended up with a little less than 1500 which had complete financial information.  
 
## Feature Engineering

##### Return on investment
The first step was to create the feature I wanted to predict.  ROI is defined as Gross - Budget over Budget.  This results in a factor indicating how many times over a production made (or lost) the money it cost to make the film.  I wanted to predict ROI because for someone with an equity stake in a project, it's clearly the most important metric.

##### Individuals contributions
My hypothesis as it relates to an individuals contributions is that one who tends to make highly profitable movies, will continue to make highly profitable movies.  To model this I calculated the mean ROI for each individual contributor to a production.  I sampled 1 director, 1 producer, and up to 5 actors for each film.  I immediatley ran into problems due to the size of my data set.  I had too many unique individuals, with too few of them having multiple credits within my dataset.  Taken directly this is an obvious source of leakage, as anyone with on credit to their name in the data set would have a perfect lateral colinier relationship with the predicted variable.  My preliminary testing with this feature had my model returning an R-squared value of .78.  In an effort to diminish the leakage, I binned the mean ROI of contributors as low, medium, and high.  While not perfect, this decreases the leakage problem.


##### Genre effects
I had 18 total genre tags present in my dataset.  These were represented as binary categories in the model and used as is.


##### Timing
I created Binary categories for both month and year of release date


##### Collaboration effects
My ultimate goal was to build networks of actors and apply some principles of social network analysis in an attempt to turn a group of people, their individual connections, and the strength between those connections into something a linear regression model could make sense of.  Eay deal right... right?  Just like rome wasn't built in a day, a graph database of 85,000+ cast and crew didn't fly out of my fingertips, and as deadlines drew ever closer, I elected to put it on hold to ensure I had a functioning model to present.


## Results
My model for this first iteration was successful at accounting for 54% of the variation present in the data set.  While this is not a terrible place to be, I know that there are some areas left to explore that should produce some significant gains.  This is still a work in progress.  I've since found more consistent sources for higher quality data, and with a larger sample set,  I'm confident that the existing features will see a strong improvement.  In addition to that I've come up with a list of features I plan on exploring:

+ **Social network**  I'm quite confident this will proce to be a valuable feature, as it can account for so many aspects of human interaction that are otherwise rather ephemeral. 


+ **Novelty** When an actor is known for repeatedly playing a certain role, for example, Bruce Willis + Action, will a novel roll, like Bruce Willis + romantic comedy be a predictor of profitability.  Similar methods could be employed as was used for in individuals relative ROI.

+ **Lesser known quantities**  actors and directors get all the hype, but a great cinematographer can take an OK script and turn it into a visual feast.  How might that effect profitability?


+ **Merchandizing**  This can turn a mild success into a financial windfall.  Disney pixar's Cars franchise is widely regarded as among their least compelling, but it is a merchandizing machine.  As much as $10 billion can be attributed to these films which blows the mind.  There are many questions that come along with this, top among them being how is this counted towards in vestors equity, if at all?  this would be a stretch, but very interesting if the data could be mined.


That's just a start.  The wonderful thing about data science is there really is no ceiling on the number of questions that can be asked and potentially answered.  Time is your only foe.  This is the beginning of this project.  It won't be the end.





[ant]: http://www.imdb.com/name/nm7153169/?ref_=fn_al_nm_3
[brian]:http://www.imdb.com/name/nm1014073/
[G]:https://en.wikipedia.org/wiki/Gigli
[tmdb]:https://www.themoviedb.org/
[tml]:http://grouplens.org/datasets/movielens/
[bom]:http://www.boxofficemojo.com/
