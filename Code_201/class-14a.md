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

For three-dimensional transforms to work, elements need a perspective from which to transform.

Perspective of an element can be set two ways:

- One way includes using the perspective value within the transform property on individual elements.
- Another includes using the perspective property on the parent element of the child elements being transformed.

#### Perspective Depth

Perspective value can be set as `none` or a length measurement.

- The `none` value turns off any perspective.
- The higher the value, the further away the perspective appears, thus creating a fairly low intensity perspective and a small three-dimensional change.
- The lower the value the closer the perspective appears, thus creating a high intensity perspective and a large three-dimensional change.

#### Perspective Origin

As with setting a `transform-origin` you can also set a `perspective-origin`. The difference between these is that the origin of a transform determines the coordinates used to calculate the change of a transform, where the origin of perspective identifies the coordinates of the vanishing point of a transform.

### 3D Transforms

Short of the `skew` transform, the 2D transforms can all be accomplished in a very similar manner we performing 3D transforms. The biggest difference being the ability to transform relative to the `Z` axis _(depth)_ as well.

#### Transform Style

When placed on a parent element, the `transform-style` property allows children elements to appear in their own three-dimensional plane. The `flat` value forces the transformed children elements to lie flat on the two-dimensional plane.

#### Backface Visibilty

By default elements are shown from the back when they face away from the screen. If we prefer not to see these elements, we set the `backface-visibility` property to `hidden`. This will hide the element whenever it is facing away from the screen.

## Transitions & Animations

Transitions provide a change from one state to another, while animations can set multiple points of transition upon different keyframes.

### Transitions

We have the potential to alter the appearance and behavior of an element whenever a state change occurs, such as when it is hovered over, focused on, active, or targeted.

For a transitrion to take place, an element must have a change in state. The easiest manner of accomplishing this is with the pseudo-classes:

- `:hover`
- `:focus`
- `:active`
- `:target`

There are four transition related properties:

- `transition-property` - determines exactly which properties will be altered. By default, all of the properties on an element will be changed. **Not all properties may be transitioned**, only those that have an identifiable halfway point.
- `transition-duration` - The duration over which a transition takes place, set using general timing values.
- `transition-timing-function` - used to set the speed in which the transition moves:
  - `linear` - moves at a constant speed from one state to the other
  - `ease-in` - starts slowly and speeds up through the transition
  - `ease-out` - starts quickly and slows down through the transition
  - `ease-in-out` - starts slowly speeds up in the middle and slows down toward the end of the transition
- `transition-delay` - sets a time value to determine how long a transition should be stalled before executing

Not all of these are required for a transition. The first three are the most commonly used.

Like the `transform` property, there are several prefixes to help us ensure the user's browser properly displays our transitions.

### Animations

Animations allow the appearance and behavior of an element to be altered in multiple keyframes.

For animation, we set multiple points at which an element should undergo a transition. this is accomplished with the `@keyframes` rule. The `@keyframes` rule includes the animation name, any animation breakpoints, and the properties intended to be animated. Different keyframe breakpoints are set using percentages, starting at 0% and working to 100% with an intermediate breakpoint at 50%.

After the keyframes have been declared, they must be identified with a name, so that an element may be assigned that animationusing the `animation-name` property.

Similiar to transitions, animations have properties for duration, timing-function and delay. They allow have an `animation-iteration-count` property. This property can determine how many times the animation occurs, including `infinite`.

In addition, the `animation-direction` property can declare whether an animation occurs in the `normal`, `reverse`, `alternate`, or `alternate-reverse` direction.

[Back to Main](../README.md)
