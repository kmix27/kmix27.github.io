---
layout: post
title:  Jupyter Notebook Automator
date:   2016-12-21 15:27:25
categories: Metis
---


I use [Jupyter notebook](http://jupyter.org/) almost exclusively in my exploration phase.  It's only when I get to the point of needing to refactor into modules or run web applications that I move over to Sublime text.  If you work with python, or any other of the rapidly expanding list of [supported languages](https://github.com/ipython/ipython/wiki/IPython-kernels-for-other-languages), I suggest you do the same. 

**The benefits are tremendous.**

I'm also a nut for efficiency and always jump at the prospect of **eliminating** repetitive tasks.  With that in mind,  I got tired of opening terminal, making sure I was in the correct directory (I like to initialize Jupyter in my root directory), then making sure I had a fresh window in Chrome, and finally running Jupyter.  
 
Far too many steps for my taste.

Follow this quick guide to package all this into an appleScript based automator app!


1. Open up Automator.  
2. Select "New Document" in the bottom left of the finder window that appears.
3. Select "Application" when prompted for the document type.

4. In the actions bar select Utilities > Run AppleScript and drag into the input panel.
5. From there, you'll want to add the following script.  It's very basic, and very easy to customize,  so have at it.  

	```applescript on run {input, parameters}
		tell application "Google Chrome"
			tell (make new window)
			end tell
			activate
		end tell
		tell application "Terminal"
			activate
			do script with command "cd ~ && jupyter notebook"
		end tell
		end run
	```
6. Hit run to test everything is working,  you should get a new terminal window open to whichever directory you chose to run Jupyter from, a new browser window will open, and Jupyter will spin up.  If everything works, save to your applications and you're done.  

I went a little further and changed the icon so I don't confuse with automator.  To do this, right click your application > Get Info > drag your desired .icns file to the top left.

I hope that this little tutorial saves you some time!



