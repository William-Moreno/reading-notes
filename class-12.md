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

## Basic Usage of Canvas

The `<canvas>` element looks similar to the `<img>` element, but has no `src` or `alt` attributes. The only attributes it does have are `width` and `height`. They are both optional and can also be arbitrarily sized with CSS or set using DOM properties. If these two attributes are not specified, the canvas will initially be **300 pixels** wide by **150 pixels** high.

**Note** - if our renderings seem distorted, we might try specifying our width and height attributes within the `<canvas>` element using attributes rather than CSS.

The `<canvas>` element can be styled with CSS, but it won't affect the actual drawing on the canvas. If no CSS rules are applied, the canvas will initially be fully transparent.

#### Fallback Content

We should always include fallback content to be displayed by older browsers that do not support `<canvas>`. We just place the fallback content inside the element. It can be a static image or a text description of the canvas content. Because of the way fallback suport is provided, a closing tag, `</canvas>`, is required, even when there is no fallback content.

### The Rendering Context

The `<canvas>` element creates a fixed-size drawing surface that exposes one or more **rendering contexts**, which are used to create and manipulate the content shown.

To display something, we need to use a method called `getContext()` on the `<canvas>` element. `getContext()` takes one parameter, the type of context, `2d` for instance, to get a `CanvasRenderingContext2D`.

## Drawing Shapes with Canvas

Once we have set up our canvas environment, we can draw rectangles, triangles, lines, arcs and curves.

### The Grid

The canvas grid is known as **coordinate space** and by default consists of a grid numbered from 0 at the top left corner of the canvas up to the width and height designated in setup (in pixels). There are ways to manipulate the grid.

Unlike **SVG**, `<canvas>` only supports two primitive shapes: rectangles and paths _(lists of points connected by lines)_. But, there are a number of path drawing functions that make it easier to compose more complex shapes.

### Rectangles

There are three functions that draw rectangles:

1. `fillRect(x, y, width, height)` - Draws a filled rectangle
1. `strokeRect(x, y, width, height)` - Draws a rectangular outline
1. `clearRect(x, y, width, height)` - Clears the specified rectangular area, making it fully transparent

`x` and `y` specify the top-left corner of the rectangle on the canvas and `width` and `length` provide the rectangle's size.

### Drawing Paths

[Back to Main](README.md)
