# Docs for the HTML `<canvas>` Element & Chart.js

---

## Chart.js

Charts are far better for displaying data visually than tables. They’re easier to look at and convey data quickly, but they’re not always easy to create.

A great way to get started with charts is with Chart.js, a JavaScript plugin that uses HTML5’s canvas element to draw the graph onto the page. It’s a well documented plugin that makes using all kinds of bar charts, line charts, pie charts and more, incredibly easy.

### Setting Up

To make use of this tool, we need to download _Chart.js_. Then copy the _Chart.min.js_ into the directory we'll be working in. Finally, we can use the HTML `<script>` tag to import the script.

### Line Charts

To draw a line chart:

- create a `<canvas>` element in HTML
- write the script to retrieve the context of the canvas
- create data for the chart
  - labels for the base of the chart
  - datasets to describe the values on the chart

### Pie Charts

To create a pie chart:

- create a `<canvas>` element in HTML
- get the context an instaniate the chart
- create the data for each section of the chart
  - a value
  - a color
- any other options

### Bar Charts

To create a bar chart (similar to a line chart):

- create a `<canvas>` element
- retrieve the element and create the graph
- add the chart's data

### Conclusion

Chart.js is simple to use and very flexible. Once we master the basics, there are many other options to discover.

[Back to Main](README.md)
