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

A path is a list of point, connected by segments of lines that can be different shapes. To make shapes using paths, we take some extra steps:

1. First, we create the path.
1. Then we use drawing commands to draw into the path.
1. Once the path has been created, we can stroke or fill the path to render it.

Functions used to perform these steps:

- `beginPath()` - Creates a new path.
- **Path methods** - to set different paths for objects.
  - `closePath` - Adds a straight line to the path, going to the start of the current sub-path
  - `stroke()` - Draws a shape by filling the path's content area.

The first step to create a path is to call the `beginPath()`. This clears any resisdent lists of sub-paths that my be stored internally.

The sedond step is calling the methods that actually speficy the paths to be drawn.

Third, is an optional step, to call `closePath()`. This method, if used, tries to close the shape by drawing a straight line from the current point to the start.

#### Eaxmple: _Triangle_

The following code draws a triangle:

```JavaScript
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.moveTo(75, 50);
    ctx.lineTo(100, 75);
    ctx.lineTo(100, 25);
    ctx.fill();
  }
}
```

### Moving the Pen

- `moveTo(x, y)` is a very useful function that moves the pen to the coordinates specified by `x` and `y`. While it is still part of the path, technically, we are essentially "_lifting the pen_".

- `lineTo(x, y)` draws a linefrom the current drawing position to the position specified.

- `arc(x, y, radius, startAngle, endAngle, anticlockwise)` draws an arc which is centered at (`x`, `y`) position with radius `radius` starting at `startAngle` and ending at `endAngle` going in the given direction indicated by `anticlockwise` _(defaults to clockwise)_.

`arcTo(x1, y1, x2, y2, radius)` draws an arc with the given control points and radius, connected to the previous point by a straight line.

### Bezier and Quadratic Curves

- `quadraticCurveTo(cp1x, cp1y, x, y)` draws a quadratic Bezier curve from the current pen position to the end point specified by `x` and `y`, using the control point specified by `cp1x` and `cp1y`.

- `bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)` draws a cubic Bezier curve from the current pen position to the end point specified by `x` and `y`, using the control points specified by (`cp1x`, `cp1y`) and (`cp2x`, `cp2y`).

- `rect(x, y, width, height)` adds a rectangular shape to the path tot he currently open path.

### Using SVG Paths

Another powerful feature of the new canvas Path2D API is using SVG path data to initialize paths on our canvas. This might allow us to pass around path data and re-use them in both, SVG and canvas.

## Applying Colors and Styles

If we want to apply colors to a shape, there are two important properties we can use: `fillStyle` and `strokeStyle`.

- `fillStyle = color` - sets the style used when filling shapes
- `strokeStyle = color` sets the style for shapes' outlines

### `fillStyle` Example

```JavaScript
function draw() {
  var ctx = document.getElementById('canvas').getContext('2d');
  for (var i = 0; i < 6; i++) {
    for (var j = 0; j < 6; j++) {
      ctx.fillStyle = 'rgb(' + Math.floor(255 - 42.5 * i) + ', ' +
                       Math.floor(255 - 42.5 * j) + ', 0)';
      ctx.fillRect(j * 25, i * 25, 25, 25);
    }
  }
}
```

### `strokeStyle` Example

```JavaScript
  function draw() {
    var ctx = document.getElementById('canvas').getContext('2d');
    for (var i = 0; i < 6; i++) {
      for (var j = 0; j < 6; j++) {
        ctx.strokeStyle = 'rgb(0, ' + Math.floor(255 - 42.5 * i) + ', ' +
                         Math.floor(255 - 42.5 * j) + ')';
        ctx.beginPath();
        ctx.arc(12.5 + j * 25, 12.5 + i * 25, 10, 0, Math.PI * 2, true);
        ctx.stroke();
      }
    }
  }
```

### Transparency

In addition to drawing opaque shapes to the canvas, we can also draw semi-transparent (translucent) shapes.

`globalAlpha = transparencyValue` - applies the specified transparency value to all future shapes drawn on the canvas. The value must be between 0.0 (full transparency) and 1.0 (fully opaque). The value is 1.0 by default.

### `globalAlpha` Example

```JavaScript
function draw() {
var ctx = document.getElementById('canvas').getContext('2d');
// draw background
ctx.fillStyle = '#FD0';
ctx.fillRect(0, 0, 75, 75);
ctx.fillStyle = '#6C0';
ctx.fillRect(75, 0, 75, 75);
ctx.fillStyle = '#09F';
ctx.fillRect(0, 75, 75, 75);
ctx.fillStyle = '#F30';
ctx.fillRect(75, 75, 75, 75);
ctx.fillStyle = '#FFF';

// set transparency value
ctx.globalAlpha = 0.2;

// Draw semi transparent circles
for (var i = 0; i < 7; i++) {
  ctx.beginPath();
  ctx.arc(75, 75, 10 + 10 * i, 0, Math.PI * 2, true);
  ctx.fill();
}
}
```

### Line Styles

There are several properties which allow us to style lines:

- `lineWidth = value`
  Sets the width of lines drawn in the future.
- `lineCap = type`
  Sets the appearance of the ends of lines.
- `lineJoin = type`
  Sets the appearance of the "corners" where lines meet.
- `miterLimit = value`
  Establishes a limit on the miter when two lines join at a sharp angle, to let you control how thick the junction becomes.
- `getLineDash()`
  Returns the current line dash pattern array containing an even number of non-negative numbers.
- `setLineDash(segments)`
  Sets the current line dash pattern.
- `lineDashOffset = value`
  Specifies where to start a dash array on a line.

### Gradients

We can also fill and stroke shapes using linear and radial gradients. We do this by creating a `CanvasGradient` object using one of two methods.

- `createLinearGradient(x1, y1, x2, y2)` - Creates a linear gradient object with a starting point of (x1, y1) and an end point of (x2, y2).
- `createRadialGradient(x1, y1, r1, x2, y2, r2)` - Creates a radial gradient. The parameters represent two circles, one with its center at (x1, y1) and a radius of r1, and the other with its center at (x2, y2) with a radius of r2.

### Patterns

Patterns can be simply created with the `createPattern()` method:

`createPattern(image, type)`

The type specifies how to use the image in order to create the pattern, and must be one of four string values:

- `repeat` - Tiles the image in both vertical and horizontal directions.
- `repeat-x` - Tiles the image horizontally but not vertically.
- `repeat-y` - Tiles the image vertically but not horizontally.
- `no-repeat` - Doesn't tile the image. It's used only once.

### Shadows

We use four properties to use shadows:

- `shadowOffsetX = float` - Indicates the horizontal distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.
- `shadowOffsetY = float` - Indicates the vertical distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.
- `shadowBlur = float` - Indicates the size of the blurring effect; this value doesn't correspond to a number of pixels and is not affected by the current transformation matrix. The default value is 0.
- `shadowColor = color` - A standard CSS color value indicating the color of the shadow effect; by default, it is fully-transparent black.

[Back to Main](../README.md)
