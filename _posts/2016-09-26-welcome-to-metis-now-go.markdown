---
layout: post
title:  Metis clock T+ 79.78 hours
date:   2016-09-26 17:06:25
categories: Metis
---

What a week.  I was excited walking into this, but I can confidently say that has only increased.  As a relatively new blogger,  it's not really a format that I'm entierly comftorble with yet, however part of the reaseon I started this whole adventure was to shake up my comfort zone,  so why not here too!

The coursework has been progressing comftorbly.  My Python at the beginning of the pre-work I would rate at a slightly advanced beginner,  and I think that was just enough.  The first week has concentrated mostly on getting everyone on the same level with some of the key tools, namely Pandas, Seaborn and Matplotlib, Git / GitHub, and the command line to name a few.  None of these were foreign to me to begin with, so working through assignments hasen't been a stretch.  I'm really glad that I took the time beforehand to read a good portion of Wes McKinney's book: [Python for Data Analysis][pfda], I really can't say enough about that book.  The Pandas documentation is pretty darn good all things said,  but having some more explicet and involved examples has really been helpful.  I know that it will continue to come in handy.

The proposition of a project due at the end of the first week was both exciting and daunting.  I actually really appreciated the pace, there wasn't really much of a ramp up,  it was more an 'ok, now go'.  It gets you in the right mindset,  and it gives you a taste of reality.  I can dream, and often my vision of what I want to create is quite ambitious. I particularly liked the short turnaround on this first project because it forced me to reconcile my dreams of what could be done with what's realistic given the constraints.  This method of thinking is a way of life within industry, so I really like how that little taste of reality was emphasized directly out of the gates.  It sets a good pace.  

The projects data set was turnstile data from the MTA of New York,  and it was an exercise in several things,  Among them:

+ Data wrangling - MTA data is nasty on a good day
+ Pitching a project - communication is key,  that was a focus.
+ Visualization - Hand in hand with communication
+ Brainstorming, and the decision making process within a group.
+ Delegation
+ Presentation of something useful in such a way as to not put your audience to sleep

I learned a lot in this project.  My group imagined the problem from the perspective of a company looking to optimize how street performers distributed themselves around New Yorks Busiest subway stations in an effort to maximize variety for the public and tips for the performers.

It was completely hypothetical,  and I'd be lying if I told you the premis wasn't picked because it was a little absurd, but I'm of the opinion that work should be fun, if it isn't, you're doing it wrong. So, given that philosophy, and the opportunity, I made it that way.  

The bulk of the effort that I put in was devoted to developing an algorithm to simulate our hypothetical goal.  We wanted to be able to first establish how many artists should be placed at any one station on any given day based on the traffic density of that station.  Once that quantity was known for a 7 day period, we assigned the artists at random into those slots, and then for each artist recorded the relative number of 'impressions' (passers by) that could be expected given their assignment.  The initial feature set included separating by type of performer so there wasn't an overabundance of one type at any one station.  Unfortunately this proved to be a little too ambitious given the rapid turnaround on this project.  

We defined a successful model as one that showed an end impressions distribution that was steeply peaked, indicating that most performers received about the same number of impressions.  The simulation was ran for 1 week, 1 month, and 1 year to see how it improved over time.  We were ultimately successful in acheiving this goal. 

Some aspects that I would change/ improve upon given more time:

+ optimization of the selection process
>The selection process didn't look at how many impressions the artist had already received.  It was purely random,  and the performance slot allotment was the driving factor in how the impressions were spread out amongst artists.  A future iteration would look at the performers historical impression count and weight them as more or less likely to receive one of the prime spots based on that.  I expect that would significantly decrease the necessary simulation period to acheive the desired results.
+ segmentation of artists
>We created a dummy dataset of artists for the purpose of this exercise, and gave them all types and subtypes.  The initial goal was to separate them based on those sub types, so that say Grand Central Station wasn't full of 6 guitarists. This could be acheived by dropping, and re- assigning any duplicates.  This wouldn't necessarily improve the model,  but it would improve the use case of the model.  
+ cleaner code
>I think this is something we can all strive for,  but when you need something that works and it's 3AM  the day before you submit,  if it runs,  it runs.  Performant code is critical though, and I know that this is something I'll only learn through doing.

All in all it was a fantastic first week.  I'm thrilled to have the opportunity to be doing something so fascinating with such interesting, intelligent, and friendly people.  


[pfda]: http://shop.oreilly.com/product/0636920023784.do
