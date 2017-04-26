---
layout: post
title:  A few handy bookmarklets for Python users
date:   2017-04-08 16:01:25
categories: Python bookmarklets
---

![](/images/bookmarklets.jpg)  

## Helpful additions to your browser!  

### What are they?

Bookmarklets are little snippets of javascript that you save as a bookmark in your browser.  They can do all kinds of useful things, and add rich customized functionality for tasks that you do regularly or repeatedly.  I've developed a few that you may find helpful.

### How do I use them?  
Very easy.  You right click on your bookmark bar within your browser and select "Add Page..."  you will get this menu:  
![](/images/bmark_menu.jpg)
From there you'll give it a name, paste the code snippet in the URL field exactly as it appears here, and select where you'd like it to live within your bookmarks.  I prefer the bookmarks bar for the stuff I use the most.  After that it's just a matter of clicking on it.  Most of these are giving you instant access to search functionality on various sites, and generally they'll give you a popup input field, and then open a new tab for the site with your input as a search term.  


## Search SkLearn Documentation  
The search on the SkLearn site is terrible,  this uses google advanced search to get you what you're looking for.   

``` Javascript
javascript:Qr=prompt('Search SciKit-Learn docs','');setTimeout( function(){ window.open('https://www.google.com/search?hl=en&as_q='+escape(Qr)+'&as_epq=&as_oq=&as_eq=&as_nlo=&as_nhi=&lr=&cr=&as_qdr=all&as_sitesearch=http%3A%2F%2Fscikit-learn.org%2F&as_occt=any&safe=images&as_filetype=&as_rights='+'') }, 10);
```  

## Search Pandas Documentation  
This takes you directly to Pandas docs search results with fewer clicks. 

``` Javascript
javascript:Qr=prompt('Search Pandas docs','');setTimeout( function(){ window.open('http://pandas.pydata.org/pandas-docs/stable/search.html?q='+escape(Qr)+'&check_keywords=yes&area=default'+'') }, 10);
```  

## Search PyPi for a package  
Sure you can do this from the command line,  but if your workflow is a jupyter notebook.  This makes finding a new/ useful package a snap.  

``` Javascript
javascript:Qr=prompt('Search  PyPi','');setTimeout( function(){ window.open('https://pypi.python.org/pypi?%3Aaction=search&term='+escape(Qr)+'&submit=search'+'') }, 10);
```  

## Search StackOverflow > Python  
Look for python specific answers to your coding questions.  

``` Javascript
javascript:Qr=prompt('Search  StackOverflow>Python','');setTimeout( function(){ window.open('http://stackoverflow.com/search?q=%5Bpython%5D'+escape(Qr)+'&submit=search'+'') }, 10);
```  

## Copy some often used text  
How many times have you typed this?  

``` python
import pandas as pd  
import numpy as np  
import matplotlib.pyplot as plt  
import seaborn as sns  
%matplotlib inline  
pd.set_option('display.max_columns',75)
```  
Well stop that.  With this one click copies a predefined chunk of text to your clipbaord.  You can then paste it straight into the top of your script and minimize unnecessary or repetative typing.  

This snippet will give you the above text to your clipboard.  

``` Javascript
javascript:!function(a){var b=document.createElement("textarea"),c=document.getSelection();b.textContent=a,document.body.appendChild(b),c.removeAllRanges(),b.select(),document.execCommand("copy"),c.removeAllRanges(),document.body.removeChild(b)}("import pandas as pd \nimport numpy as np \nimport matplotlib.pyplot as plt \nimport seaborn as sns \n%matplotlib inline\npd.set_option('display.max_columns',75)");
```  

You can put whatever text you want in there by editing the snippet. @autor string, setting options, whatever you want.  Replace the string in the last set of parens with a string of your chosing.  You'll need to explicitely type linebreaks with "\n".  

That's just a tiny taste of what you can do with bookmarklets.  The possibilites for customization are endless, allowing for some pretty neat stuff to happen with just a click.  I hope you find some of these useful!  



