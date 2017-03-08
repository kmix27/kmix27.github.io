---
layout: post
title:  I built trellogd for your job search
date:   2017-03-07 16:01:25
categories: job hunt
---



Today I learned how to pip!  
Not in the sense of using it as a package manager,  that's water well under the bridge.  I learned how to pip to share what I'm doing and contribute to the open source community,  and it feels fantastic!  
   
I've been working on my job search, and I have been using [Trello](https://trello.com) for the purpose of organization and record keeping.  If you aren't familiar with it I suggest you check it out.  It's a simple, clean, and incredibly flexible hub for organization of anything you can think of.  What's better is they have a great [API](https://developers.trello.com/) and there is a good stable [python wrapper](https://pypi.python.org/pypi/py-trello/0.9.0) for interacting with it.  
Given all that, I wanted to create a simple command line tool to act as a pipeline from a glass door job listing, to a consistent, organized, and feature rich addition to the trello board of my choosing.  

I came up with [**trellogd**](https://github.com/kmix27/trello_glassdoor).  

I released the tool in a very basic form last week, and today I got around to getting it up on [PyPi](https://pypi.python.org/pypi/trellogd/0.1) so that anyone who wants to use Trello for their job search has an easy tool to accomplish that.  

The build was pretty straightforward.  Nothing too crazy.  It was a great opportunity to learn more about git/Github, setuptools, web-scraping, API's, and of course argparse.  I found that building command line tools is fun and can be tremendously handy.  Right now the scope of what this tool is capable of is rather limited, see the [README](https://github.com/kmix27/trello_glassdoor/blob/master/README.md) for more details on usage, but I have a list of stuff I'd like to add:  

* Expand the functionality to work with alternate listings on glass door  
* Add additional job listing sites
* increase automation via a bookmarklet, browser extension or an automator app.  

Nothing particularly earth shattering or DataSciencey, but it was a good opportunity for several things to happen:  

* Further round out my Python skill set  
* Gain a better understanding of how applications are built and shipped
* Make an efficient, automated solution for a problem I currently face regularly  

If I had to come up with the biggest challenge I faced within this project I think it would probably be finding the right python wrapper for the api.  I spent longer than I should have trying to figure out/ completely re-write [py-trello](https://pypi.python.org/pypi/trello/0.9.1).  Which I believe is an auto generated wrapper.  They have the best name and the top spot on PyPi which is a shame, because the code doesn't work.  biggest lesson to takeaway from that (and one that is re-enforced a lot) if something seems screwey or doesn't make sense, do some more searching.  Ten minutes more research may well save you hours.


I am trying to focus more on contributing to my Github.  It's rather sparse, despite the hundreds of hours I've put into python. I really need to push a lot more to not only share what I'm doing with the open source community, but to prove myself capable as a developer and a Data Scientist.  Lots more like this to come! 


