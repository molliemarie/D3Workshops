# Let's build a bar plot!

We'll be creating our first bar plot using Chicago crime data, which is available on the [Chicago Data Portal](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-present/ijzp-q8t2). For creation of this plot, I have aggregated the data to find the total counts of each type of crime for each year. (See ipython notebook where I did this [here](data/transformChiCrimeData.ipynb).) Before getting started, open the data file (`ChiCrime.csv`) to see how the data is structured.

We're going to create a bar plot, showing the counts of each crime in Chicago. It will end up looking something like this:

![static scatter](imgs/finishedBar2018.png)

TKTK: change starter steps.

And, here we go!

**Note:** Since [Mike Bostock](https://bost.ocks.org/mike/) (creator of d3.js) doesn't technically make valid HTML pages, we're not going to either — here's how we'll start our own empty HTML pages from here on out:

  ```
  <!DOCTYPE html>
  <meta charset="utf-8">

  <style type="text/css">
    /*css to go here*/
  </style>

  <body></body>

 <script src="https://d3js.org/d3.v4.min.js"></script>
 
  <script>
    //JS to go here
  </script>

  ```
  
## Steps:

1. First, go to [this project's blocksbuilder link](https://blockbuilder.org/molliemarie/22c1107f4226f64cba9df6a1f4e09408) and fork it. You'll notice the code is set up like above, plus I've added styling that will add a pink border around any svg we might draw.

  ```
  svg {
    border: 1px solid #f0f;
  }
  ```
  
  **Other things to note:**
  
  First, we're using the the `d3.csv()` module of [`d3-request`](https://github.com/d3/d3-request) to load in our data. This allows us to load in data from a csv file; the module transforms it from it's current format to the json format that d3.js likes. 
  
  ```
  // Reading in data here, then calling "ready" function:
  d3.csv("ChiCrime.csv", ready)
  ```
  
  Additionally, the code is being formatted so that it will be easier to use later. 
  
  ```
  data.forEach(function(d) {
    d.count = +d.count; //making sure count reads as a number
    d.year = +d.year; //making sure year reads in as a number
    d.violation = d['Primary Type']; //changing to an easier to use variable name
  });
  ```
  
  And lastly, we're only going to work with 2018 data today, so I've created a variable for 2018 filtered data.
  
  ```
    // filtering for 2018 data
  var data2018 = data.filter(function(d) { return d.year == 2018})
  ```
  
  
2. think about the format we want our data in.
3. Add an SVG element of width 720 and height 400.
4. Using a data join, add a `circle` for every element of our array. Give it a radius 5 and a class, `ufoCircle'. Inspect it in the console. (You can pull up a Javascript console by clicking console in the bottom left corner of the pen)
 5. Position the circles based on their `cx` and `cy` attributes. How does SVG interpret these positions?
 6. We'll need to add a [scale](https://github.com/d3/d3-scale/blob/master/README.md).
 7. Let's label the count of each using text. At this point, we'll talk about how we can avoid this second data join and make our code a bit more efficient.
 8. Redo the original join, using groups first, then appending circles and text. Note SVG [transformation](http://www.w3.org/TR/SVG/coords.html) documentation, which is not that fun. 
 9. Maybe [axes](https://github.com/d3/d3-axis/blob/master/README.md) are in order?  
 10. We might need to move our axes around. We'll go through the math. Also, maybe add some styles?
 11. The margins are a problem, and they will always be. Here's [a great trick](https://bl.ocks.org/mbostock/3019563) we'll use on every chart we make from here on out.
  
  
