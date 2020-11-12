# CSS Transforms, Transitions, and Animations

---

## Transforms

CSS3 brought new ways to position and alter elements. These new techniques are made possible using the `transform` property.

The `transform` property has two settings:

- two-dimensional
- three dimensional

Generally speaking, browser support for the `transform` property is not great. The fix for this problem appears to be to write transform declarations in the following manner to ensure that our styling is properly rendered by the user's browser:

```CSS
div {
  -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
}
```

The order here has the last declaration in place to overwrite any of the others if the browser being used fully supports the `transform` property.

### 2D Transforms

Two-dimensional transforms work on the `x` and `y` axes, known as the horizontal and vertical axes.

- `rotate();` - provides the ability to rotate an element from 0 to 360 degrees. _(positive - clockwise, negative - counterclockwise)_. The default point of rotation is the center of the element.

- `scale[X or Y]();` - allows us to change the appeared size of an element. the default value is 1. It is possible to scale just the height or width of the element by including either `X` or `Y` immediately following `rotate`.

- `translate[X or Y]();` - will change the position of an element on the horizontal axis `[X]` or on the vertical axes `[Y]`.

- `skew[X or Y]();` - will distort elements on the horizontal axis, vertical axis, or both.

#### Combining Transforms

To combine transforms, list the transform values within the transform property one after the other without the use of commas.

Using multiple transform declarations will not work, as each declaration will overwrite the one above it.

### Transform Origin

The default transform origin is the dead center of an element, both 50% horizontally and 50% vertically. To change this default origin position the `transform-origin` property may be used.

The `transform-origin` property can accept one or two values. When only one value is specified, that value is used for both the horizontal and vertical axes. If two values are specified, the first is used for the horizontal axis and the second is used for the vertical axis.

_Note_ - the `transform-origin` property can run into issues when also using the `translate` transform property value.

### Perspective

[Back to Main](README.md)
