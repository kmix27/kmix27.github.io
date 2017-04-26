---
layout: post
title:  Microformats for webscraping
date:   2017-04-13 16:31:25
categories: webscraping python
---

# Microformats  

**What are they?**  
Microformats are a set of standard approaches to HTML/XHTML markup which allows data inteded for an end user on a browser to be easily accessed by a machine.  Think universal API for certain types of data baked into a websites markup.  You probably use them everyday without even realizing it.  For example [hCard](https://en.wikipedia.org/wiki/HCard) is a microformat for representing contact information.  It shares the exact same formatting as vCard which is a standard used nearly everywhere contact information is utalized. 

**What does that mean for me?**  
Say you are building acorpus of recipes to study the use or prevelance of certain ingredients.  The [hRecipe](https://en.wikipedia.org/wiki/HRecipe) microformat will make the task of identifying and parsing recipes across the web a much simpler task than it would have been in the absence of a universal formatting schema.   

---  
### Types of microformats  
For a full list, see the [Wiki](https://en.wikipedia.org/wiki/Microformat)  here's a few to take note of:  

1. [microdata](https://en.wikipedia.org/wiki/Microdata_(HTML))
2. [hNews](https://en.wikipedia.org/wiki/HNews)
3. [hProduct](https://en.wikipedia.org/wiki/HProduct)
4. [hReview](https://en.wikipedia.org/wiki/HReview)

Among others

---

### Schemas

[Schema.org](http://schema.org/) is a project whose goal is to provide consistent and universal structures for formatting data in markup.  Elements of a page that are stored using those schemas will often reference the exact schema being applied, making the job of parsing the data greatly simplified.  

---

### How can I use them?  

Now that you know about these very useful hidden secrets of HTML.  You'll want to make use of them.  How you do that is really up to you,  but there are a few tools that might help you along the way.

* [mf2py](https://github.com/tommorris/mf2py) Is a microformat parser written in Python.  For websites containing microformats,  this can make accessing them as JSON or dictionaries a simple exercise.  

* [microdata](https://github.com/edsu/microdata) is a python package that can parse microdata (surprise).  It's capable of returning a JSON object which has the effect of converting an end user site to a reasonably well structured API. 

* [microform.at](http://microform.at/)* is a PHP based tool for detecting the presence of the various types of microformats in a given URL.  It's available on [github here](https://github.com/WebOrganics/TransFormr) as of this writing the web app was down.  

* [microformats.org](http://microformats.org/) has tons of information about all available microformats and current news regarding their evolution.



