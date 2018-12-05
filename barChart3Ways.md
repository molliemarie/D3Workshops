# Make the same bar plot in three different ways!

You'll be making the same bar plot in three different ways. Each time, you will end up something that looks like this:

![bar plot](imgs/barplot.png)

**Note:** Since Mike doesn't [technically](https://bl.ocks.org/mbostock/3885304) make valid HTML pages, we're not going to either.

## Part I: Using HTML to make a bar plot

This is an exercise to practice basic HTML, SVG, and CSS syntax. It is also designed to demonstrate that something that _looks like_ a chart on a website is actually just a collection of simple HTML elements. 

You'll want to open up [this pen](https://codepen.io/molliemarie/pen/GdJYRx), fork it, and then perform the following steps (instructions are also in the file):

1) Make a container `<div>` in which you'll render your content 
2) Create a `<p>` element in which you write "My Bar Chart" 
3) Make a container `<svg>` element in which you'll place your rectangles 
- Set your svg's `width` to 300, and `height` to `400` 
4) Put 3 `<rect>` elements inside of your `<svg>`, setting the properties for each one: 
    - `x`: How far to move the rectangle in the `x` direction (right). Should be `0` for all rectangles. 
    - `y`: How for to move the rect in the `y` direction (down from the top). Should be `10`, `40` `70` 
    - `width`: How far to draw the rectangle to the right. Should be `100`,`200`, `300` 
    - `height`: The vertical height of each rectangle. Should be `20` for all rectangles 

5) In the `<style>` section, set `rect` elements to have a "fill" of "purple"

## Part II: Using D3 to make a bar plot

This is an exercise to practice manipulating the DOM with D3. 

You'll want to open up your [this pen](https://codepen.io/molliemarie/pen/BxNGEp), fork it, and perform the following steps (instructions are also in the file). All steps will be completed using d3.js, and should be completed in the `<script>` section at the bottom of the file.

1) Select your `body` and append a `div` element in which you'll render your content. To do this, you'll use the `d3.select()` method, and then the `.append()` method to append your element to your selection.
2) Append a new `p` element to the `div` you just created, and use the `.text()` method to set the text to "My Bar Chart"
3) Append a container `svg` to your `div` element in which you'll place your rectangles 
- Set your svg's `width` to 300, and `height` to `400` 
4) Append 3 `rect` elements inside of your `<svg>` (one at a time), setting the properties for each one. We'll improve on this process later: 
    - `x`: How far to move the rectangle in the `x` direction (right). Should be `0` for all rectangles. 
    - `y`: How for to move the rect in the `y` direction (down from the top). Should be `10`, `40` `70` 
    - `width`: How far to draw the rectangle to the right. Should be `100`,`200`, `300` 
    - `height`: The vertical height of each rectangle. Should be `20` for all rectangles 

## Part III: Using D3 AND Data Joins to make a bar plot

This is an exercise to practice manipulating the DOM D3 using the **[data-join](https://bost.ocks.org/mike/join/)**. 

You'll want to open [this pen](https://codepen.io/molliemarie/pen/rvVoMP), fork it, and then perform the following steps (instructions are also in the file). All steps will be completed using d3.js, and should be completed in the `<script>` section at the bottom of the file. Preliminary steps have been completed for you.

1) Append 3 `rect` elements inside of your `<svg>` **using the data join**. To do this, you'll use the following syntax:

```js
// Select all rects in the svg and bind your data to the selection
var rects = svg.selectAll('rect')

// Determine what's new to the screen using `.enter()` and for each new element, append a rectangle
// Then, use the data provided to set the desired attributes
rects.data(data)
    .enter()
    .append('rect')
    .attr('x', 0)
    .attr('height', 20)
    .attr('y', function(d,i){return d.y}) // use y attribute to drive layout
    .attr('width', function(d,i){return d.width}); // use width attribute to drive layout
    

```
    - `x`: How far to move the rectangle in the `x` direction (right). Should be `0` for all rectangles. 
    - `y`: How for to move the rect in the `y` direction (down from the top). Should be `10`, `40` `70` 
    - `width`: How far to draw the rectangle to the right. Should be `100`,`200`, `300` 
    - `height`: The vertical height of each rectangle. Should be `20` for all rectangles 
