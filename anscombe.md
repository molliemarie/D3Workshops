# Anscombe Quartet Scatter Plot - Part One

Now that we have had a chance to explore Anscombe's Quartet a bit, let's plot it out with D3! :D

We'll make a fairly basic plot with no interactions to start that will end up looking something like this:

<img src="imgs/anscombe1.png" width="500px;"/>

**Note:** Since Mike doesn't [technically](https://bl.ocks.org/mbostock/3887118) make valid HTML pages, we're not going to either — here's how we'll start our own empty HTML pages from here on out:

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
  
  **Steps:**
  
1. First, go to [this pen](https://codepen.io/molliemarie/pen/ELjrmN?editors=1000) and fork it. You'll notice the code is set up like above, plus I've added styling that will add a pink border around any svg we might draw.

  ```
  svg {
    border: 1px solid #f0f;
  }
  ```
  
2. Make a Javascript object out of your tabular data and make sure you know how to manipulate it. (This is an annoying but useful exercise in getting useful in a text editor. Here's instructions on how to do [multiple selections with codepen](https://blog.codepen.io/2014/03/25/spring-editor-upgrades/).) I'll use the data from the group number II, but you should chart whatever you drew.

Once you're done with it, it should look something like this: 
```
var data = [
  {"group": "II", "x":10, "y" : 9.14},
  ...
  {"group": "II", "x":5, "y" : 4.74}
];
```

3. Add an SVG element of width 720 and height 400.
4. Using a data join, add a `circle` for every element of our array. Give it a radius 5 and a class, `anscombe-circle'. Inspect it in the console. (You can pull up a Javascript console by clicking console in the bottom left corner of the pen)
 5. Position the circles based on their `x` and `y` attributes. How does SVG interpret these positions?
 6. We need a [scale](https://github.com/d3/d3-scale/blob/master/README.md). Let's go over a quick [talk]() (tktk, add slides) about scales, and then create one!
 7. Let's label the coordinate positions of each using text. At this point, we'll talk about how we can avoid this second data join and make our code a bit more efficient.
 8. Redo the original join, using groups first, then appending circles and text. Note SVG [transformation](http://www.w3.org/TR/SVG/coords.html) documentation, which is not that fun. 
 9. Maybe [axes](https://github.com/d3/d3-axis/blob/master/README.md) are in order?  
 10. We might need to move our axes around. We'll go through the math. Also, maybe add some styles?
 11. The margins are a problem, and they will always be. Here's [a great trick](https://bl.ocks.org/mbostock/3019563) we'll use on every chart we make from here on out.
 12. Let's style the chart to match our drawing. Things like [tickSize](https://github.com/d3/d3-axis/blob/master/README.md#axis_tickSize) might help.
 13. Let's add a [sequential colorscale](https://github.com/d3/d3-scale#sequential-scales) for fun.
 
 Alright, we've done a lot! What we have should look pretty similar now to the plot above. Unfortunately, though, our chart isn't really better than what we get with the free tools. (Paste your data into [Chartbuilder](http://quartz.github.io/Chartbuilder/) and feel free to weep.) What makes D3 different is its ability to create **dynamic** visualizations and things that tools aren't designed to create.

Later on, we can come back to this plot and make it interactive!
