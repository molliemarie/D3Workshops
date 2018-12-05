# Create Your First D3.js Scatter Plot!

This repo holds resources from an introductory talk and workshop on D3.js. Presented by Mollie Pettit at a [Chicago Data Viz Community](https://www.meetup.com/Chicago-Data-Viz-Community/) event on [Create your first D3.js scatter plot!](https://www.meetup.com/Chicago-Data-Viz-Community/events/255637315/).

Connect with Mollie: [twitter](https://twitter.com/MollzMP) // [email](mailto:molliempettit@gmail.com) // [linkedin](https://www.linkedin.com/in/molliempettit/)

# Getting Set Up

## Join D3.js Slack
If you haven't yet, join the Chicago Data Viz Community Slack ([bit.ly/ChiDataVizSlackInvite](https://join.slack.com/t/chicagodataviz/shared_invite/enQtNDY0ODMzNDU0OTE5LTgyYjYwNDA1ZjA1MTZhZjk5MGRjOGY4OTU2YWVmYmQ1MDMwMTJmYTQ5NzRlZTRkYWI3ZGUxODJhYTZkYzhjNTA)) and join the following channels:

- **#workshops** - for sharing links during the workshop
- **#D3js** (optional) - for chatting about D3 going forward

## CodePen
You’ll need a CodePen account to participate in the workshop exercises fully. You can [get one for free here](http://codepen.io/). 

Once you've joined, you can find all of the codepends necessary for this workshop [here](https://codepen.io/collection/XwdbBJ/).

# Introduction to D3.js

## Slides

- [Why Do We Visualize?](https://github.com/molliemarie/SharedSlides/blob/master/WhyWeVisualize.pdf)
- [What is D3.js? / When should I use it?](https://github.com/molliemarie/SharedSlides/blob/master/whatIsD3.pdf)

## Further Learnings / Fancy Examples
Further learnings and fancy examples [located here](../d3examples.md).

# Ok, Let's get coding!

## Exercise: Make the same scatter plot in three different ways!

In these exercises you will be making the same bar plot in three different ways: 

- Using HTML, CSS, and SVG
- Using D3.js
- Using D3 AND data joins

## Exercise: [Building our first scatter plot](../anscombe.md)

We'll now build our first full chart by plotting one of the Ambscombe data sets in a scatter plot.

# Local Servers

We won't be using a local server today, but if you're going to be toying around with D3 a lot, you'll want to use a text editor and a local server rather than coding in codepen.

## Getting Started with a Local Server

1. Download "starter.html" and "ufo.csv" and save it in a folder
2. Use Terminal (Mac) or Command Prompt (PC), which both represent the command line, and you'll want to go to the folder you added the files to.
	* For both Macs and PCs, you'll use the ```cd``` command 
3. Once there, start a local server 
	* For Macs, you can simply run: ``` python -m http.server 8000 ``` if using python 3; ``` python -m SimpleHTTPServer 8000```\* if using python 2
	* For PCs, it's a bit more complicated. You'll need to either download python or XAMPP. You can checkout [this page](https://www.apachefriends.org/index.html)
4. Go to your browser (Chrome is recommended), and go to this URL ```localhost:8000```\*

\*Can substitute out `8000` for any other number.

#### Note on Local Servers: 

In some cases, you can view local HTML files directly in your web browser. However, some browsers have restrictions that prevent them from loading local files via JavaScript, for security reasons. That means if your D3 code is trying to pull in any external datafiles (like CSVs or JSON), it will fail with no good explanation. This isn’t D3’s fault; it’s a browser feature that prevents loading of scripts and other external files from third-party, untrusted websites.

For this reason, it is much more reliable to load your page via a web server. Although you could use a remote web server, it is much, much faster to store and host everything locally (meaning, on the same computer, the one right in front of you). It is a strange idea, to use your local computer to host and serve files to itself, but you can think about it as the different programs talking to each other: the browser program requests files from the server program, which responds by serving them back.

# Helpful links used during workshop
 * [Margin Conventions](https://bl.ocks.org/mbostock/3019563)
 * [Data Joins](https://bost.ocks.org/mike/join/)
 * [Chaining Syntax](http://alignedleft.com/tutorials/d3/chaining-methods)
 * [How Selections Work](https://bost.ocks.org/mike/selection/)
 * [Adding Stuff and Understanding Selections](http://www.jeromecukier.net/blog/2011/08/09/d3-adding-stuff-and-oh-understanding-selections/)
 * [D3 Scales](http://alignedleft.com/tutorials/d3/scales)
 * [D3 Axes](http://alignedleft.com/tutorials/d3/axes)
 * [Scatterplot example](https://bl.ocks.org/mbostock/3887118)
 * [D3 Path](https://www.dashingd3js.com/svg-paths-and-d3js)
